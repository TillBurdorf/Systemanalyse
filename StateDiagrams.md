---
title: Buchung
---
stateDiagram-v2
    [*] --> open: buchungErstellen()
    open --> open: sitzplätzeWählen()
    open --> storniert: 30 min vor Vorstellung
    open --> bezahlt: buchungAbschließen()
    bezahlt --> storniert: buchungStornieren()
    bezahlt --> [*]: Vorstellung vorbei
    storniert --> [*]

---
title: Ticket
---
stateDiagram-v2
    [*] --> ungültig: sitzplätzeWählen()
    ungültig --> gültig: buchungAbschließen()
    gültig --> abgeschlossen: validieren(), ticketStornieren(), Vorstellung vorbei
    ungültig --> abgeschlossen: ticketStornieren()
    abgeschlossen --> [*]
