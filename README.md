# solarflow_2400AC_control
Automatische Leistungsregelung für den Zendure SolarFlow 2400 AC+, die anhand der aktuellen Netzleistung selbstständig zwischen Laden, Entladen und Standby wechselt, um den Netzbezug bzw. die Einspeisung möglichst gegen null zu regeln. Dabei werden SOC-Grenzen, OffGrid-Verbraucher, dynamische Stromtarife sowie verschiedene Sicherheits- und Plausibilitätsprüfungen berücksichtigt.


Usecase:
- Dynamischer Stromtarif
  - Laden wenn Strom günstig

- Off Grid Steckdose als USV für z.B.: Serverschrank.
  - SOC Backup als Reserve bei Stromausfall. (Min SOC der Solarflow schaltet bei erreichen die Off Grid steckdose ab)


Helfer Definition:
-P1-Historie*
input_text Helper zur Speicherung der letzten Netzleistungswerte.
Typ: Text-Eingabe (input_text)
name: Zendure P1 History
symbol: mdi:clipboard-text-clock
min: 0
max: 100

-Timestamp-Helper*
input_number Helper zur Speicherung des Unix-Timestamps der letzten Zendure-Aktion.
Typ: Zahlenwert-Eingabe (input_number)
name: Zendure timestamp
symbol: mdi:timelapse
min: 0
max:9999999999
step: 1
Eingabefeld


Optionale Helfer:
-Backup SOC
Optionaler input_number Helper mit der zusätzlichen SOC-Reserve. Wenn kein Helper ausgewählt wird, wird Min SOC verwendet.
name: Zendure Backup SoC
symbol: mdi:battery-medium
min: 10 (niemals unter SOCmin stellen)
max: 50 (Niemals über SOCset stellen)
step: 5
Schieberegler
Maßeinheit: %

