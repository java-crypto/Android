# 1 Erzeugung des Impfzertifikates

Die Erzeugung des Impfzertifikates erfolgt über eine in gängigen Browsern aufrufbare Webseite im HTML-Format. Die Umwandlung der Daten in einen QR-Code erfolgt mittels Javascript.

Das digitale Impfzertifikat beginnt mit der Erfassung einiger personengebundener Daten (Vor- und Nachname sowie Geburtsdatum des Impflings) sowie der Impfstoff-gebundenen Daten (Hersteller, Impfstoff sowie gegebenenfalls der Chargennummer).

Hinzu kommen die Informationen über das Impfdatum, die Information über die notwendige Anzahl von Impfdosen (z.B. die Anzahl 2 bei BioNTech/Comirnaty) und der Vollständigkeit der Impfung, verbunden mit einer Gültigkeit der (vollständigen) Impfung (hier gehen wir von einem Jahr Gültigkeit aus).

Abgerundet wird der Datensatz mit einer Information über den genutzten Signaturalgorithmus, den Zeitstempel der Signaturerstellung und die digitale Signatur selber. Der verwendete Signaturalgorithmus ist RSA mit PKCS1.5 Padding und SHA-256 Hashwert. Der notwendige private RSA-Schlüssel ist im Programm fest kodiert - es handelt sich um einen Beispielschlüssel, der ansonsten nirgendwo verwendet wird.  Bitte beachtet für eigene Programme, das die ungeschützte Speicherung eines privaten Signaturschlüssels hochgradig unsicher ist.

Alle aufgeführten Daten werden in einen QR-Code kodiert und auf dem papiergebundenen Ausdruck dokumentiert.

Ich habe keinerlei interne Verknüpfung oder Prüfung der Datenfelder eingebaut. Dadurch ist es möglich, den Impfstoffhersteller (z.B. AstraZeneca) mit dem Produktnamen eines anderen Herstellers (z.B. Comirnaty von BioNTech) zu mischen. Ebenso erfolgt keine Dosiszuordnung zu den Produktnamen und der Vollständigkeit der Impfung (Beispiel: Der Impfstoff von BioNTech benötigt 2 Impfungen für einen vollständigen Impfschutz, es kann aber zum Beispiel "1/1" und "Vollständig: Ja" erfasst werden). Hinsichtlich der Datumsangaben wird ebenfalls keine Prüfung vorgenommen und auch die Eingabefelder sind nicht für Datumsangaben maskiert, so das auch Fantasiedaten eingegeben werden können (z.B. der "35.13.2345").
Sourcecode:

Der vollständige Programmcode inklusive der verwendeten Bibliothek ist in meinem GitHub-Archiv abrufbar: https://github.com/java-crypto/Android/tree/main/Impfzertifikat/Erzeugung.
Screenshot zum Programm:

Hinweis zum nachfolgenden Bild: mit einem Klick auf das Bild öffnet sich eine größere Darstellung:


Lizenzinformationen:

Ein Hinweis zum Lizenzstatus aller drei Module: die von mir erstellten Programme stehen unter der UNLICENSE-Lizenz und können beliebig genutzt werden.  Einige notwendige Programm-Bibliotheken (wie z.B. für Erzeugung oder Auswertung von QR-Codes) werden unter Fremdlizenzen genutzt, bitte beachtet die jeweiligen Hinweise.

Das Programm verwendet die Bibliothek "qrcodejs" zur Erstellung des QR-Codes. Das Copyright dafür liegt beim Autor "Sangmin, Shim ", der die Bibliothek unter der MIT-Lizenz bereitstellt. Die Bibliothek ist unter der Adresse https://github.com/davidshimjs/qrcodejs abrufbar. Die MIT-Lizenz können Sie unter diesem Link abrufen: https://github.com/davidshimjs/qrcodejs/blob/master/LICENSE.

Das Wort QR Code ist ein eingetragenes Warenzeichen der DENSO WAVE INCORPORATED, der Lizenztext ist hier zu finden: http://www.denso-wave.com/qrcode/faqpatent-e.html


<b>Lizenzen:</b><br><br>Das Programm verwendet die Bibliothek "qrcodejs" zur Erstellung des QR-Codes. Das Copyright dafür liegt beim Autor "Sangmin, Shim ", der die Bibliothek unter der MIT-Lizenz bereitstellt. Die Bibliothek ist unter der Adresse <a href="https://github.com/davidshimjs/qrcodejs" target="_blank">https://github.com/davidshimjs/qrcodejs</a> abrufbar. Die MIT-Lizenz können Sie unter diesem Link abrufen: [MIT_LICENSE.MD](MIT_LICENSE.MD).
<br>

Das Wort "QR Code" ist ein eingetragenes Warenzeichen der DENSO WAVE INCORPORATED, den Lizenztext können Sie hier aufrufen: <a href="http://www.denso-wave.com/qrcode/faqpatent-e.html" target="_blank">http://www.denso-wave.com/qrcode/faqpatent-e.html</a>
<br><br>

Die HTML-Datei ist unter der **UNLICENSE-Lizenz** veröffentlicht.

Die vollständige Dokumentation ist hier zu finden: http://java-crypto.bplaced.net/impfzertifikaterzeugung/
