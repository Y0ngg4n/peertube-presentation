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
zoom: 1.5
layout: default-4
---
# Was ist Peertube?
- Open Source Videoplattform
- Activitypub-Föderation aka *Fediverse*
- P2P-Übertragungen via WebRTC
<QualleMitVideo class="absolute right-5% bottom-5%" width="20%" />

<!-- 
P2P = Peer-to-Peer
Activitypub = Protokol mit dem z.Bsp. Mastodon und Pixelfed miteinander reden
-->
---
transition: slide-left
zoom: 1.5
layout: default-2
---
# Warum sollte ich Peertube benutzen?
- Datenschutz
- Fediverse
- Freie Software unterstützen
<Qualle class="pt-20 absolute right-5% bottom-5%"/>

<!--
Datenschutz: Youtube und Co. benutzen Tracking und Algorithmen für Vorschläge
-->
---
zoom: 0.9
layout: default-3
---
# Wie Funktioniert Peertube denn?
```mermaid
graph TD
    A[PeerTube Site A] <-->|Teilt Inhalte| B[PeerTube Site B]
    A <-->|Teilt Inhalte| C[PeerTube Site C]
    B <-->|Teilt Inhalte| C
    
    User1[Sie] -->|Seite beitreten| A
    User1 -->|Kann Videos von allen Seiten anschauen| B
    User1 -->|Kann Videos von allen Seiten anschauen| C
    
    style A fill:#ffe6e6
    style B fill:#e6ffe6
    style C fill:#e6e6ff
    style User1 fill:#f9f9f9
```
---
layout: right
---
# Wie spart Peertube Bandbreite und verhindert Überlastung?
<div class="grid grid-cols-2 gap-4">
```mermaid
flowchart LR
    subgraph "Traditionelle Videoplattformen"
        S1[Video Server] -->|Sendet Video| V1[Zuschauer 1]
        S1 -->|Sendet Video| V2[Zuschauer 2]
        S1 -->|Sendet Video| V3[Zuschauer 3]
    end
    
    style S1 fill:#ffcccc
    style V1 fill:#f9f9f9
    style V2 fill:#f9f9f9
    style V3 fill:#f9f9f9
```
```mermaid
flowchart LR
    subgraph "PeerTube's Weg"
        PS[PeerTube Server] -->|Sendet Video| PV1[Zuschauer 1]
        PS -->|Sendet Video| PV2[Zuschauer 2]
        PV1 -->|Hilft das Video zu senden| PV2
        PV1 -->|Hilft das Video zu senden| PV3[Zuschauer 3]
        PV2 -->|Hilft das Video zu senden| PV3
    end
    
    style PS fill:#ccffcc
    style PV1 fill:#f9f9f9
    style PV2 fill:#f9f9f9
    style PV3 fill:#f9f9f9
```
</div>
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
