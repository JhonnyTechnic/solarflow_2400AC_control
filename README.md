# solarflow_2400AC_control
Automatische Leistungsregelung für den Zendure SolarFlow 2400 AC+, die anhand der aktuellen Netzleistung selbstständig zwischen Laden, Entladen und Standby wechselt, um den Netzbezug bzw. die Einspeisung möglichst gegen null zu regeln. Dabei werden SOC-Grenzen, OffGrid-Verbraucher, dynamische Stromtarife sowie verschiedene Sicherheits- und Plausibilitätsprüfungen berücksichtigt.


Usecase:
- Dynamischer Stromtarif
  - Laden wenn Strom günstig

- Off Grid Steckdose als USV für z.B.: Serverschrank.
  - SOC Backup als Reserve bei Stromausfall. (Min SOC der Solarflow schaltet bei erreichen die Off Grid steckdose ab)

