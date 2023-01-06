# Persönliche Benutzerwörterbücher für Word

In diesem Repository befinden sich meine medizinischen
Benutzerwörterbücher für Word. Das Vokabular ist ganz überwiegend in
Deutsch. Inhaltlich liegt der Schwerpunkt auf internistischen und
nephrologischen Begriffen.

Nachdem mir kürzlich meine Benutzerwörterbücher abhanden gekommen sind
und es offenbar keine freien zum Herunerladen gibt, habe ich
beschlossen, in diesem Repository eine Art öffentliches Backup zu
pflegen. Deshalb sind diese Wörterbücher auch als "work in progress" zu
betrachten, sie wachsen im Zuge meiner Arbeit.

Das Repository wird in unregelmäßigen Abständen Updates erhalten.

Die Wörterbücher dürfen gerne von jedermann bzw. jederfrau für private
oder akademische  Zwecke verwendet werden, jegliche Verwendung erfolgt
jedoch auf eigenes Risiko und ohne Gewähr.

Die Wörterbücher enthalten möglicherweise geschützte Bezeichnungen und
Marken. Vor einer Verwendung dieser Termini müssen ggf. die Bedingungen
der Rechterinhaber beachtet werden.

## Technische Hinweise zu Word-Benutzerwörterbüchern

Word (zumindest die Windows-Version) speichert Benutzerwörterbücher als
Textdateien mit UTF-16-LE-Kodierung und versieht die Dateien zudem mit
einem Byte Order Mark (BOM). Git kommt mit solchen Dateien nicht so gut
zurecht. Ich habe versucht, ob Word auch UTF-8 ohne BOM akzeptiert,
dies ist jedoch nicht der Fall. Deshalb habe ich in der Datei
[.gitattributes](.gitattributes) ein paar Regeln für den Umgang mit
`*.dic`-Dateien aufgestellt. Diese funktionieren aber nicht völlig
autark. Wer ein Diff der Wörterbücher sehen möchte, sollte bitte den
folgenden "diff driver" in seiner/ihrer Git-Konfiguration
(`~/.gitconfig`) definieren:

    [diff "utf16diff"]
      textconv = iconv -f utf-16 -t utf-8

<!-- vim: set wrap ai sts=2 tw=72 : -->
