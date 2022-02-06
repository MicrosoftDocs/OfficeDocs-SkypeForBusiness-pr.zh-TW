---
title: Edge 電腦設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要以單一 Edge Server 或 Edge 集區中的成員電腦的身分編輯 Edge Server 電腦的屬性，請設定伺服器名稱及 IP 位址設定設定：
---

# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edge 電腦設定展開工具 (適用於 Lync Server 2010)
 
若要以單一 Edge Server 或 Edge 集區中的成員電腦的身分編輯 Edge Server 電腦的屬性，請設定 **伺服器名稱及 IP 位址** 設定設定：
  
- **內部名稱或 FQDN**：輸入網域名稱系統 (DNS) 中所參照的電腦名稱稱。 
    
- **Internal IPv4 address**：輸入這部電腦之內部網路介面卡 (NIC) 的 IPv4 位址。
    
- 設定與此電腦相關聯的 **Access Edge service** **外部 IPv4 位址**
    
    > [!IMPORTANT]
    > 如果您選擇使用單一 IP 位址進行 Edge Server 設定，則只能編輯 Access Edge service 的外部 IPv4 位址。 其他 Edge 服務會與 Access Edge service 共用相同的 IPv4 位址。 
  
- 若可編輯，請設定 **Web 會議服務** 與此電腦相關聯的 **外部 IPv4 位址**
    
- 若可供編輯，您可以設定與此電腦相關聯的 **A/V Edge service** **外部 IPv4 位址**
    
- 若可供編輯，請設定與此電腦相關聯且 **已啟用 NAT 的公用 IPv4 位址** 。
    
    > [!IMPORTANT]
    > 只有在您選擇為 A/V Edge service 提供網路位址轉譯 (NAT) 時，才可編輯 **啟用 NAT 之公開 IPv4 位址** 的 configuration 屬性。
  
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

