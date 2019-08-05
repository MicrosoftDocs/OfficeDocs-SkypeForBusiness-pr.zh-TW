---
title: 定義用來判斷商務用 Skype Server 中的位置的網路元素
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 規劃您在商務用 Skype Server Enterprise Voice 中, 要將哪些網路元件對應至 E9 的位置, 以進行部署。
ms.openlocfilehash: a68f1517d038f82e62a7aca3ef909e4e67d25e4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187618"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>定義用來判斷商務用 Skype Server 中的位置的網路元素
 
規劃您在商務用 Skype Server Enterprise Voice 中, 要將哪些網路元件對應至 E9 的位置, 以進行部署。
  
如果您要設定商務用 Skype 伺服器基礎結構以支援自動用戶端位置偵測, 您必須首先決定要使用哪些網路元素將呼叫者對應至位置。 在商務用 Skype Server 中, 您可以將下列第2層和第3層網路元素與位置建立關聯:
  
- 無線存取點 (WAP) 基本服務集標識 (BSSID) 位址 (第2層)
    
- LLDP 切換埠 (第2層)
    
- LLDP 切換主機殼識別碼 (第2層)
    
- IP 子網 (第3層)
    
- 用戶端 MAC 位址 (第2層)
    
網路元素會依優先順序順序列出。 如果您可以使用一個以上的網路元素來找出用戶端, 商務用 Skype Server 會使用優先順序順序來決定要使用哪種機制。 
  
下列各節提供使用每個網元的詳細資料。
  
> [!IMPORTANT]
> 當您使用網路元素將呼叫者對應到位置時, 將位置資訊服務資料庫保持在最新狀態, 這是一項非常重要的重要性。 例如, 如果您新增或變更網路元素 (例如新增 WAP), 則必須刪除舊專案, 並在位置資料庫中新增新的專案。 
  
## <a name="wireless-access-point"></a>無線存取點

當用戶端以無線方式連線到網路時, 位置要求會使用 WAP 的 BSSID 位址來決定其位置。 如果用戶端是漫遊, 則所指示的 WAP 可能不是最接近的物件, 而且您甚至可以在建築物的不同基底, 挑選一個 WAP。 若要指出位置是近似值, 您可以在 location 值前面加上 **[Near]** 或 **[Closeto]** 描述項。
  
這個位置方法假設每個 WAP 的 BSSID 都是靜態的。 不過, 如果您的 WAP 供應商使用的是動態指派的 BSSIDs, 則從 WAP 取得的 BSSID 可能會變更 (在 WAP 設定變更之後, 可能會發生這種情況), 而且無線用戶端可能不會收到位置。 若要防止這種可能性, 您必須使用 ERLs, 為每個 WAP 所使用的所有可能的 BSSID 位址填入位置資訊服務資料庫。 
  
## <a name="lldp-ports-and-switches"></a>LLDP 埠和交換器

支援連結層探索通訊協定的受管理乙太網交換器: 媒體端點探索 (LLDP-MED-V) 可將其身分識別和埠資訊宣告至 LLDP 相容的用戶端, 然後可以針對 location 資料庫進行查詢, 以提供裝置的位置。 您可以將 ERLs 完全與交換器主機殼識別碼相關聯, 或者您可以將它們對應到埠層級。
  
> [!NOTE]
> 商務用 Skype 伺服器支援使用 LLDP-MED-V 來判斷只有 Lync Phone Edition 裝置和商務用 Skype 用戶端在 Windows 8 上執行的位置。 如果您需要使用交換器層級的第2層資料來判斷其他有線電腦版商務用 Skype Server 用戶端的位置, 您必須使用用戶端 MAC 位址方法。 
  
## <a name="subnet"></a>端子

第3層 IP 子網提供所有商務用 Skype Server 用戶端所支援的機制, 可讓您自動偵測用戶端位置。 使用 IP 子網是設定及管理有線用戶端最簡單的位置方法。 不過, 在您決定要使用子網之前, 請先使用下列問題來協助判斷子網的位置是否正確, 才能準確找到用戶端:
  
- 一或多個用戶端子網涵蓋多個地面嗎？
    
- 一個或多個子網是否涵蓋了多個建築物？
    
- 每個用戶端子網上所覆蓋的占地空間是多少？
    
如果子網覆蓋範圍太寬, 您可能需要使用其他機制來尋找用戶端。 不過, 如果您有任何實際的情況, 我們建議客戶重組其 IP 子網, 以符合 ERL 位置的具體需求, 而不是產生協力廠商 SNMP 解決方案的成本與複雜性。
  
## <a name="client-mac-address"></a>用戶端 MAC 位址

若要使用用戶端電腦的 MAC 位址來尋找來電者, 您需要受管理的乙太網交換器, 而且您必須部署可探索連線至 (或透過) 這些交換器之商務用 Skype 用戶端的 MAC 位址的協力廠商 SNMP 解決方案。 SNMP 解決方案會持續輪詢受管理的交換器, 以取得連線至每個埠的端點 MAC 位址的目前對應, 並取得對應的埠識別碼。 在商務用 Skype 用戶端的位置資訊服務要求期間, 位置資訊服務會使用用戶端的 MAC 位址來查詢協力廠商應用程式, 然後傳回任何相符的切換 IP 位址和埠識別碼。 位置資訊服務會使用此資訊來針對相符記錄查詢其發佈的 Layer 2 wiremap, 並將位置傳回給用戶端。 如果您使用這個選項, 請確認 SNMP 應用程式與發佈的位置資料庫記錄之間的切換埠識別碼一致。
  
> [!NOTE]
> 某些協力廠商 SNMP 解決方案可以支援未受管理的存取交換器;如果服務商務用 Skype 用戶端的開關是未受管理的, 但有一個上行連結到受管理的發佈交換器, 則受管理的交換器可以向 SNMP 應用程式傳回連接至 access 開關之用戶端的 MAC 位址。 此資訊可讓位置資訊服務識別使用者的位置。 不過, 您可以只將單一 ERL 指派給非託管交換器上的所有埠, 因此只有在存取開關的主機殼層級 (而非埠層級) 才能使用位置的最高值。 
  

