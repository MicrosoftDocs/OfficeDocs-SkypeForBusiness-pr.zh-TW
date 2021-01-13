---
title: 定義用來判斷商務用 Skype Server 中的位置的網路元素
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 規劃用於將來電者對應至 E9-1-1 部署中商務用 Skype Server Enterprise Voice 之位置的網路元件時所需的決策。
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813633"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>定義用來判斷商務用 Skype Server 中的位置的網路元素
 
規劃用於將來電者對應至 E9-1-1 部署中商務用 Skype Server Enterprise Voice 之位置的網路元件時所需的決策。
  
如果您設定商務用 Skype Server 基礎結構以支援自動用戶端位置偵測，您必須先決定要用來將來電者對應至位置的網路元素。 在商務用 Skype Server 中，您可以將下列 Layer 2 和 Layer 3 網路元素與位置相關聯：
  
- 無線存取點 (WAP) 基本服務組識別碼 (BSSID) 位址 (第 2 層)
    
- LLDP 交換器連接埠 (第 2 層)
    
- LLDP 交換器底座識別碼 (第 2 層)
    
- IP 子網路 (第 3 層)
    
- 用戶端 MAC 位址 (第 2 層)
    
網路元素會依照優先順序列出。 如果使用一個以上的網元可以找到用戶端，商務用 Skype 伺服器會使用優先順序的順序來決定要使用的機制。 
  
下列各節會詳細說明每個網路元素的使用方式。
  
> [!IMPORTANT]
> 當您使用網元將來電者對應至位置時，將位置資訊服務資料庫保持在最新狀態，這會是最為重要的。 例如，如果您新增或變更網路元素 (如新增 WAP)，則必須在位置資料庫中刪除舊項目並增加新項目。 
  
## <a name="wireless-access-point"></a>無線存取點

當用戶端連線至無線網路時，「位置要求」會使用 WAP 的 BSSID 位址來判斷位置。 如果用戶端是漫遊，則表示的 WAP 可能不是最接近的狀態，而且也可以拾取位於不同的大樓地板的 WAP。 若要指出位置是大致的，您可以在 location 值的前面加上 **[Near]** 或 **[Closeto]** 描述項。
  
此位置方法會假定每個 WAP 的 BSSID 為靜態。 不過，如果您的 WAP 廠商使用的是以動態方式指派的 BSSIDs，則從 WAP 取得的 BSSID 可能會變更 (在 WAP 設定變更) 之後可能會發生此情況，而且無線用戶端可能會在不會收到位置的情況下留下。 若要避免這種可能性，您必須使用 Erl 填入 Location 資訊服務資料庫，以取得每個 WAP 所使用的所有可能的 BSSID 位址。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 連接埠和交換器

支援 Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) 之受管理的乙太網路交換器，可將其識別碼及連接埠資訊公告至相容於 LLDP-MED 的用戶端，您可依位置資料庫查詢用戶端以提供裝置的位置。您可以僅在交換器底座辨識碼上建立 ERL 的關聯，或者可將其對應至連接埠層級。
  
> [!NOTE]
> 商務用 Skype Server 支援使用 LLDP-MED，判斷只有 Lync Phone Edition 裝置和在 Windows 8 上執行之商務用 Skype 用戶端的位置。 如果您需要使用交換器層級2資料來判斷其他有線電腦型商務用 Skype Server 用戶端的位置，您必須使用用戶端 MAC 位址方法。 
  
## <a name="subnet"></a>子網路

第3層 IP 子網可提供所有商務用 Skype Server 用戶端所支援的機制，以自動偵測用戶端位置。 使用 IP 子網路是設定與管理有線用戶端之最容易的方法。 決定使用子網路前，請先詢問自己下列問題來判斷子網路的位置是否明確到足以正確定位用戶端：
  
- 一個或多個用戶端子網路是否涵蓋多個樓層？
    
- 一個或多個子網路是否涵蓋多棟建築？
    
- 每個用戶端子網路涵蓋多少樓層空間？
    
如果子網路涵蓋的區域太廣，您可能必須使用其他機制尋找用戶端。但是，以實際應用而言，建議您重新組織其 IP 子網路連線以符合 ERL 位置的精確性需求，才不會提高協力廠商 SNMP 解決方案的成本和複雜性。
  
## <a name="client-mac-address"></a>用戶端 MAC 位址

若要使用用戶端電腦的 MAC 位址來尋找來電者，您需要受管理的乙太網參數，而且您必須部署協力廠商的 SNMP 解決方案，以探索連線至 (或透過) 那些參數的商務用 Skype 用戶端 MAC 位址。 SNMP 解決方案會持續輪詢受管理交換器以取得連線至每個連接埠之端點 MAC 位址目前的對應，以及取得對應的連接埠識別碼。 在商務用 Skype 用戶端對位置資訊服務的要求中，位置資訊服務會使用用戶端的 MAC 位址查詢協力廠商應用程式，然後傳回任何相符的交換器 IP 位址和埠 IDs。 位置資訊服務使用此資訊來查詢其發佈的第2層線路圖，以取得相符的記錄，並將位置傳回給用戶端。 如果您使用此選項，請確認 SNMP 應用程式以及已發行的位置資料庫記錄之間的交換器連接埠識別項是一致的。
  
> [!NOTE]
> 某些協力廠商的 SNMP 解決方案可支援未受管理的存取參數;如果服務商務用 Skype 用戶端的參數未受管理，但有連結至受管理的發行參數，則受管理的參數可以傳回 SNMP 應用程式連接至 access 參數的用戶端 MAC 位址。 此資訊可讓位置資訊服務識別使用者的位置。 不過，可能只會將單一 ERL 指派至未受管理之交換器上的所有連接埠，所以只有在存取交換器的底座層級才能取得明確的位置，而非連接埠層級。 
  

