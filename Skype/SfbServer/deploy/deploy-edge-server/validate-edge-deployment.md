---
title: 驗證您在商務用 Skype Server 中的邊緣部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要：瞭解如何確認您的 Edge 伺服器或 Edge 伺服器池部署在商務用 Skype Server 中是否正常運作。
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768296"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>驗證您在商務用 Skype Server 中的邊緣部署
 
**摘要：** 瞭解如何確認您的 Edge 伺服器或 Edge 伺服器池部署在商務用 Skype Server 中是否正常運作。
  
部署 Edge 伺服器或 Edge 伺服器池之後，您必須知道它是否正常運作。 以下是一些可協助您確認 Edge 環境與內部伺服器連線的情況，而且您的外部使用者也可以透過您的邊緣連線到您的商務用 Skype Server 環境。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>驗證內部伺服器與邊緣伺服器之間的連線性

當安裝邊緣伺服器時，在 Edge 伺服器或 Edge 伺服器池中自動進行連線驗證，您仍然可以使用 Windows PowerShell 確認此操作。 在具有中央管理存儲的內部伺服器上執行 CsManagementStoreReplicationStatus Cmdlet，或在已安裝商務用 Skype Server Core 元件（OcsCore .msi）的已加入網域的電腦上執行。
  
執行此命令的初始結果可能會為複製提供 False 狀態，而不是 True。 如果發生這種情況，請執行 CsManagementStoreReplication Cmdlet。 請提供一些時間來完成複製，然後再次執行 CsManagementStoreReplicationStatus Cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>驗證外部使用者的連線性

我們有一個不錯的工具，可用於確認 Edge 伺服器設定，以及能夠連線、傳送及接收邊緣伺服器案例的正確訊息。 這是[遠端連線 Anaylzer 的網站](https://testconnectivity.microsoft.com/)。 這是由 Microsoft 支援服務管理和維護的網站。 若要使用此工具，請流覽至該網站，然後依照指示選擇適合您的案例。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>測試外部使用者連線性時的考慮事項

針對外部使用者存取的任何測試，都必須包含貴組織支援的每一種內部使用者類型，其中可能包含下列任一或所有專案：
  
- 至少一個聯盟網域中的使用者（我們建議您將它們全部測試）。
    
- 匿名使用者。
    
- 貴組織中已登入商務用 Skype 但無法使用 VPN 的使用者。
    
這些測試會判斷您的邊緣伺服器是否為：
  
- 從您的網路外部使用 telnet 用戶端來偵聽必要的埠。
    
  - 例如： telnet sip.contoso.com 443
    
  - 您應該針對您在 Edge 伺服器或 Edge 伺服器池中所使用的埠執行上述測試，視您的部署而定。
    
- 執行正確的外部 DNS 解析。
    
  - 從您的網路外部，ping Edge 伺服器或 Edge 伺服器池中的每個外部 Fqdn。 即使 ping 失敗，您也會看到 IP 位址，您可以將您之前指派的 IP 位址進行比較。
    

