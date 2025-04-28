---
theme: shibainu
title: Peertube im Fediverse
info: |
  Präsentation über Peertube
class: text-center
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
layout: cover
---
# Peertube
## Eine Alternative zu den Videoplattformen der Tech-Riesen

<img width="30%" class="mx-auto" src="/images/fresh-news-mobile.webp"/>
---
transition: slide-left
layout: default-4
---
<Transform scale="1.3">

# Was ist Peertube?
- Open Source Videoplattform
- Activitypub-Föderation aka *Fediverse*
- P2P-Übertragungen via WebRTC

</Transform>
<QualleMitVideo class="absolute right-5% bottom-5%" width="20%" />
<!-- 
P2P = Peer-to-Peer
Activitypub = Protokol mit dem z.Bsp. Mastodon und Pixelfed miteinander reden
-->
---
transition: slide-left
layout: default-3
---

# Warum sollte ich Peertube benutzen?
- Datenschutz
- Fediverse
- Freie Software unterstützen
- [Plugins](https://joinpeertube.org/plugins-selection) und Themes
- Keine Werbung
- Kein Alghoritmus
- Videobearbeitungsmöglichkeiten
  - Video mit Start und Ende schneiden
  - Intro und Outro hinzufügen
  - Wasserzeichen/Logo einfügen
- Livestreams
- Externe Videos auf die eigene Instanz synchronisieren
<Qualle class="pt-20 absolute right-5% bottom-5%"/>
<!--
Datenschutz: Youtube und Co. benutzen Tracking und Algorithmen für Vorschläge
-->
---
layout: center
---
# Wie funktioniert Peertube denn?
<Transform scale="1" class="">

```mermaid
graph TD
    A[PeerTube Site A] <-->|Teilt Inhalte| B[PeerTube Site B]
    A <-->|Teilt Inhalte| C[PeerTube Site C]
    B <-->|Teilt Inhalte| C
    
    User1[Nutzer] -->|Seite beitreten| A
    User1 -->|Kann Videos von allen Seiten anschauen| B
    User1 -->|Kann Videos von allen Seiten anschauen| C
    
    style A fill:#9ED8DB,stroke:#2980B9,color:#333333
    style B fill:#FEEE7D,stroke:#F39C12,color:#333333
    style C fill:#FF9E9D,stroke:#E74C3C,color:#333333
    style User1 fill:#FFC36B,stroke:#E67E22,color:#333333
```

</Transform>
---
layout: default-2
---
# Wie spart Peertube Bandbreite und verhindert Überlastung?
<Transform scale="1.2">
<div class="absolute grid grid-cols-2 gap-4 mr-15">

```mermaid
flowchart LR
    subgraph "Traditionelle Videoplattformen"
        S1[Video Server] -->|Sendet Video| V1[Zuschauer 1]
        S1 -->|Sendet Video| V2[Zuschauer 2]
        S1 -->|Sendet Video| V3[Zuschauer 3]
    end
    
    style S1 fill:#FF9E9D,stroke:#E74C3C,color:#333333
    style V1 fill:#FFC36B,stroke:#E67E22,color:#333333
    style V2 fill:#FFC36B,stroke:#E67E22,color:#333333
    style V3 fill:#FFC36B,stroke:#E67E22,color:#333333

```
```mermaid
flowchart LR
    subgraph "PeerTube"
        PS[PeerTube Server] -->|Sendet Video| PV1[Zuschauer 1]
        PS -->|Sendet Video| PV2[Zuschauer 2]
        PV1 -->|Hilft das Video zu senden| PV2
        PV1 -->|Hilft das Video zu senden| PV3[Zuschauer 3]
        PV2 -->|Hilft das Video zu senden| PV3
    end
    style PS fill:#9ED8DB,stroke:#2980B9,color:#333333
    style PV1 fill:#FEEE7D,stroke:#F39C12,color:#333333
    style PV2 fill:#FEEE7D,stroke:#F39C12,color:#333333
    style PV3 fill:#FEEE7D,stroke:#F39C12,color:#333333
```
</div>
</Transform>
---
---
# Peertube unterstützt verteilte Systeme
<Transform scale="0.95">

```mermaid
flowchart TD
    A[PeerTube-Instanz] --> B{Benötigt Videoverarbeitung?}
    B -->|Ja| C[Sendet Auftrag an Remote Runner]
    C --> D[Remote Runner verarbeitet Video]
    D --> E[Remote Runner sendet verarbeitetes Video zurück]
    E --> F[PeerTube aktualisiert Video-Metadaten]
    
    subgraph "Remote Runner Aufgaben"
        G[Transkodierung]
        H[Videokonvertierung]
        I[Untertitelerzeugung]
        J[Video-Optimierung]
    end
    
    C --- G
    C --- H
    C --- I
    C --- J
    
  
    style A fill:#9ED8DB,stroke:#2980B9,color:#333333
    style B fill:#FF9E9D,stroke:#E74C3C,color:#333333
    style C fill:#FEEE7D,stroke:#F39C12,color:#333333
    style D fill:#FEEE7D,stroke:#F39C12,color:#333333
    style E fill:#FEEE7D,stroke:#F39C12,color:#333333
    style F fill:#9ED8DB,stroke:#2980B9,color:#333333
    style G fill:#FFC36B,stroke:#E67E22,color:#333333
    style H fill:#FFC36B,stroke:#E67E22,color:#333333
    style I fill:#FFC36B,stroke:#E67E22,color:#333333
    style J fill:#FFC36B,stroke:#E67E22,color:#333333
```

</Transform>
---
layout: section
transition: slide-up
---
# Hilfreiches Tool: Instanzübergreifende Suche
[Suche: https://joinpeertube.org/browse-content](https://joinpeertube.org/browse-content)
<QualleSearch class="absolute right-5% top-5%" width="20%" />
---
layout: iframe
url: https://joinpeertube.org/browse-content
---
--- 
layout: default
---
# Wie funktioniert die Suche?

<Transform scale="1.4">

```mermaid
flowchart TD
    A[Nutzer] -->|Sucht nach Videos| B[PeerTube-Instanz]
    B -->|Lokale Suchanfrage| C[Lokale Datenbank]
    B -->|Globale Suchanfrage| D[SepiaSearch]
    
    D -->|Indiziert Videos von| E[PeerTube-Instanz 1]
    D -->|Indiziert Videos von| F[PeerTube-Instanz 2]
    D -->|Indiziert Videos von| G[PeerTube-Instanz 3]
    D -->|Indiziert Videos von| H[... viele weitere Instanzen]
    
    C -->|Lokale Ergebnisse| B
    D -->|Globale Ergebnisse| B
    B -->|Kombinierte Suchergebnisse| A
    
    style A fill:#FFC36B,stroke:#E67E22,color:#333333
    style B fill:#9ED8DB,stroke:#2980B9,color:#333333
    style C fill:#FEEE7D,stroke:#F39C12,color:#333333
    style D fill:#FF9E9D,stroke:#E74C3C,color:#333333
    style E fill:#DDDDDD,stroke:#7F8C8D,color:#333333
    style F fill:#DDDDDD,stroke:#7F8C8D,color:#333333
    style G fill:#DDDDDD,stroke:#7F8C8D,color:#333333
    style H fill:#DDDDDD,stroke:#7F8C8D,color:#333333
```

</Transform>
---
transition: slide-left
layout: section-3
---
# Wie benutze ich Peertube denn?
<QualleFrage class="absolute right-5% top-5%"/>
<!-- Live-Demo -->
---
transition: slide-up
layout: default-5
---
# Klingt cool, wo kann ich starten?
- Videos benötigen viel Speicherplatz, deshalb schwer Instanz zu finden die Registrierung zulässt.
- Die geschlossene Registrierung schützt die Platformbetreiber
- Zum Anschauen von Videos benötigt man kein Konto
<QualleFrage class="absolute right-5% bottom-5%"/>

## Instanzen mit offener Registrierung
- [Peertube Instanz-Liste unter https://joinpeertube.org/instances](https://joinpeertube.org/instances)
- [Adminforge: clip.place](https://clip.place/)
- [edutainment content: tilvids.com](https://tilvids.com/)
- [Musik: v.basspistol.org](https://v.basspistol.org)
<!-- 
Auf der Digitalcourage-Instanz ist die Registrierung auch nicht offen und wir werden sie auch zum aktuellen Zeitpunkt nicht öffnen
-->
---
transition: slide-left
layout: iframe
url: https://joinpeertube.org/instances
---
---
transition: slide-up
layout: section
---
# Kann ich vielleicht meine 
# eigene Instanz installieren?
<img width="15%" class="absolute top-5% right-5%" src="/images/QualleComputer.png">
---
transition: slide-up
layout: iframe
url: https://docs.joinpeertube.org/install/any-os
---
---
layout: iframe
url: https://docs.joinpeertube.org/install/docker
---
---
layout: quote
---
<img width="20%" class="absolute right-3% top-3%" src="/images/fresh-news-mobile.webp"/>

# Danke für
<br/>
<br/>

# eure Aufmerksamkeit
---
layout: section-2
---
# Habt ihr
# noch Fragen?
<QualleFrage class="absolute right-5% bottom-5%"/>
---
layout: default-6
---
# Quellen
- https://joinpeertube.org/
- https://www.davidrevoy.com/data/images/blog/2023/2023_peertube-generator.jpg
