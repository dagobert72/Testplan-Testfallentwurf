# 🧪 Testplan & Testfallentwurf für GroceryMate

## Testobjekt (System unter Test)
**Webshop:** [https://grocerymate.masterschool.com/](https://grocerymate.masterschool.com/)  

Die neuen Funktionen, die getestet werden sollen, sind:
1. **Warenkorb-Speicherung** (Persistenz über Sessions hinweg)  
2. **Produkt-Suchfunktion mit Filtern** (Preis, Kategorie, Verfügbarkeit)  
3. **Checkout mit Rabattcode-Funktion**  

---

# 📋 Testplan

## 1. Analyse des Produkts
Der Webshop **GroceryMate** ermöglicht den Online-Einkauf von Lebensmitteln. Mit den neuen Features sollen Benutzerfreundlichkeit, Flexibilität und Conversion Rate gesteigert werden.  
- Kunden können Waren im Warenkorb speichern, auch nach Logout/Login.  
- Produkte können über Suchfilter gezielt gefunden werden.  
- Rabattcodes können im Checkout angewendet werden.  

---

## 2. Entwurf der Teststrategie
- **Testarten:**  
  - Funktionale Tests (Prüfung der korrekten Umsetzung der Funktionen)  
  - Usability-Tests (Bedienbarkeit der neuen Features)  
  - Regressionstests (Sicherstellen, dass bestehende Funktionen nicht beeinträchtigt sind)  
  - Automatisierte Tests für Kernprozesse (Warenkorb, Checkout)  

- **Testmethoden:**  
  - Black-Box-Testing  
  - Äquivalenzklassenbildung  
  - Grenzwertanalyse  

---

## 3. Definition der Testziele
- Sicherstellen, dass die **Warenkorb-Speicherung** zuverlässig funktioniert.  
- Verifizieren, dass die **Produktsuche mit Filtern** korrekte Ergebnisse liefert.  
- Prüfen, dass die **Rabattcode-Funktion** fehlerfrei arbeitet (korrekte Berechnung, Validierung).  

---

## 4. Testkriterien
- **Abnahmekriterien:**  
  - Alle definierten Testfälle für die neuen Funktionen wurden erfolgreich durchgeführt.  
  - Keine kritischen oder hohen Fehler offen.  

- **Abbruchkriterien:**  
  - Mehr als 30% der Testfälle schlagen fehl.  
  - Blockierende Bugs verhindern die Durchführung.  

- **Fortsetzungskriterien:**  
  - Fehler wurden priorisiert und dokumentiert.  
  - Blocker wurden behoben.  

---

## 5. Ressourcenplanung
- **Team:** 1 Testmanager, 2 Tester, 1 Entwickler zur Bugfix-Unterstützung  
- **Tools:** Jira (Testmanagement), Selenium/PyTest (Automatisierung), GitHub (Versionierung)  

---

## 6. Planung der Testumgebung
- Testsystem: Staging-Server des Webshops  
- Browser: Chrome, Firefox, Safari  
- Devices: Desktop, Tablet, Smartphone  
- Daten: Testuser, Testprodukte, gültige/ungültige Rabattcodes  

---

## 7. Zeitplan & Aufwandsschätzung
- Analyse & Testfalldesign: 2 Tage  
- Manuelle Tests: 3 Tage  
- Automatisierte Tests: 2 Tage  
- Bugfix & Retests: 2 Tage  

Gesamt: **~9 Tage**  

---

## 8. Testliefergegenstände (Deliverables)
- Testplan  
- Testfälle (Excel/Jira)  
- Bugreports  
- Testprotokolle  
- Abschlussbericht  

---

# 🧾 Testfallentwurf (Test Case Design)

## Funktion 1: Warenkorb-Speicherung
**Ziel:** Prüfen, ob Artikel nach Logout/Login im Warenkorb bleiben.  

| Testfall | Beschreibung | Erwartetes Ergebnis | Testentwurfs-Technik | Automatisierbar |
|----------|--------------|----------------------|----------------------|-----------------|
| TC1.1 | Artikel in den Warenkorb legen, Logout, Login | Artikel ist noch im Warenkorb | Äquivalenzklassenbildung | ✅ |
| TC1.2 | Mehrere Artikel hinzufügen, Browser schließen, erneut öffnen | Warenkorb enthält alle Artikel | Szenariobasiert | ✅ |
| TC1.3 | Artikel löschen, Logout/Login | Artikel ist auch nach Login entfernt | Zustandsübergangstest | ✅ |

---

## Funktion 2: Produktsuche mit Filtern
**Ziel:** Prüfen, ob die Such- und Filterfunktion korrekt arbeitet.  

| Testfall | Beschreibung | Erwartetes Ergebnis | Testentwurfs-Technik | Automatisierbar |
|----------|--------------|----------------------|----------------------|-----------------|
| TC2.1 | Suche nach Produktname „Apfel“ | Nur Produkte mit „Apfel“ erscheinen | Äquivalenzklassenbildung | ✅ |
| TC2.2 | Filter nach Preis < 5€ | Nur Produkte ≤ 5€ erscheinen | Grenzwertanalyse | ✅ |
| TC2.3 | Kombination Filter „Bio + verfügbar“ | Nur verfügbare Bio-Produkte angezeigt | Kombinationstest | ✅ |

---

## Funktion 3: Checkout mit Rabattcode
**Ziel:** Verifizieren der Rabattcode-Validierung und Preisberechnung.  

| Testfall | Beschreibung | Erwartetes Ergebnis | Testentwurfs-Technik | Automatisierbar |
|----------|--------------|----------------------|----------------------|-----------------|
| TC3.1 | Eingabe gültigen Codes „SAVE10“ | 10% Rabatt wird abgezogen | Äquivalenzklassenbildung | ✅ |
| TC3.2 | Eingabe ungültigen Codes „XXXX“ | Fehlermeldung: „Ungültiger Code“ | Negativtest | ✅ |
| TC3.3 | Eingabe abgelaufenen Codes | Fehlermeldung: „Code abgelaufen“ | Grenzwertanalyse (Datum) | ✅ |

---

# 📌 Fazit
- Der Testplan definiert **Umfang, Ziele, Ressourcen und Kriterien**.  
- Der Testfallentwurf deckt die drei neuen Funktionen mit **jeweils mindestens 3 Testfällen** ab.  
- Alle Kern-Testfälle sind **automatisierbar**, da sie wiederholbar und deterministisch sind.  
