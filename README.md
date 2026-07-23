# Zabbix & Discord Alerting Integration

## 📖 O projekcie
Krótki opis projektu: Konfiguracja monitoringu Zabbix w celu wysyłania natychmiastowych powiadomień (alertów) o awariach infrastruktury bezpośrednio na kanał Discord z użyciem Webhooków. Projekt symuluje realne środowisko produkcyjne, w którym zespół IT jest informowany o problemach w czasie rzeczywistym.

## 🏗️ Architektura
Monitorowany Host ➡️ Zabbix Server ➡️ Zabbix Webhook ➡️ Discord Channel

## 🛠️ Wykorzystane technologie
* Zabbix 7.0.28
* Discord API (Webhooks)
* Linux / Windows Server (do hostowania Zabbixa)

---

## ✅ Rezultat (Efekt końcowy)
Tak prezentują się alerty dostarczane bezpośrednio na kanał zespołu:

![<img width="1527" height="937" alt="image" src="https://github.com/user-attachments/assets/ed7bd6bc-0900-4eaf-b3dc-734007e13ae8" />
]()

---

## 🚀 Instrukcja konfiguracji (Krok po kroku)

### Krok 1: Konfiguracja Webhooka na Discordzie
1. Wejdź w ustawienia kanału na Discordzie (ikona zębatki).
2. Przejdź do **Integracje** -> **Webhooki** -> **Nowy Webhook**.
3. Skopiuj wygenerowany URL Webhooka.

<details>
  <summary>📸 Pokaż zrzut ekranu</summary>
  
  ![<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/5a520f14-4bea-41a1-b03f-519bfedba4f9" />
]()
</details>

### Krok 2: Aktywacja Media Types w Zabbix
1. W Zabbix przejdź do **Administration** -> **Media types**.
2. Znajdź integrację **Discord** i upewnij się, że jej status to *Enabled*.

<details>
  <summary>📸 Pokaż zrzut ekranu</summary>
  
  ![<img width="1265" height="781" alt="image" src="https://github.com/user-attachments/assets/9be8fba2-c2ae-4551-9aae-8241f6bc8532" />
]()
</details>

### Krok 3: Powiązanie Webhooka z użytkownikiem
1. Przejdź do **Administration** -> **Users** i wybierz konto administratora.
2. W zakładce **Media** dodaj nowe powiadomienie typu Discord i wklej skopiowany wcześniej URL.

<details>
  <summary>📸 Pokaż zrzut ekranu</summary>
  
  ![<img width="611" height="732" alt="image" src="https://github.com/user-attachments/assets/d390273c-fef9-4d59-9d28-84961d805b9c" />
]()
</details>

### Krok 4: Włączenie akcji reagowania na awarie (Actions)
1. Przejdź do **Configuration** -> **Actions** -> **Trigger actions**.
2. Włącz domyślną regułę *Report problems to Zabbix administrators*.

<details>
  <summary>📸 Pokaż zrzut ekranu</summary>
  
  ![<img width="1697" height="672" alt="image" src="https://github.com/user-attachments/assets/f6594202-1458-4c2c-a176-b7d07d7ec328" />
]()
</details>

---

