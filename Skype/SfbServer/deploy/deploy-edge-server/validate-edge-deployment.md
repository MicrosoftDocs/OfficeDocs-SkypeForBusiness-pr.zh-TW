---
title: 在商務用 Skype Server 中驗證 Edge 部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要：瞭解如何驗證 Edge server 或 edge server 集區的部署在商務用 Skype Server 中是否正常運作。
ms.openlocfilehash: 175baab9770e6013820e0e632712bf75b7669a57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583237"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>在商務用 Skype Server 中驗證 Edge 部署
 
**摘要：** 瞭解如何驗證 Edge server 或 edge server 集區的部署在商務用 Skype Server 中是否正常運作。
  
部署 Edge Server 或 Edge Server 集區之後，您必須知道其是否運作正常。 以下是一些可協助您確認 Edge 環境連線至內部伺服器的一些事項，此外，您的外部使用者還是可以透過 Edge 連接至您的商務用 Skype Server 環境。
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>驗證內部伺服器和 Edge server 之間的連線能力

在安裝 Edge Server 時，會自動在 Edge Server 或 Edge Server 集區中進行連線驗證，但您仍然可以使用 Windows PowerShell 對此進行確認。 在具有中央管理存放區的內部伺服器上，或在已安裝商務用 Skype Server 核心元件 (OcsCore.msi) 的任何已加入網域的電腦上執行 Get-CsManagementStoreReplicationStatus Cmdlet。
  
執行這個命令的初始結果可能會提供錯誤狀態，而非 True 用於複寫。 如果發生這種情況，請執行 Invoke-CsManagementStoreReplication Cmdlet。 請提供一些時間來完成複寫，然後再次執行 Get-CsManagementStoreReplicationStatus Cmdlet。
  
## <a name="verify-connectivity-for-your-external-users"></a>驗證外部使用者的連線能力

我們確實有一個不錯的工具可以確認 Edge Server 設定，以及能夠為 Edge Server 案例連線、傳送及接收正確訊息的功能。 它是 [Remote Connectivity Anaylzer 網站](https://testconnectivity.microsoft.com/)。 這是由 Microsoft 支援人員所管理及維護的網站。 若要使用此工具，請流覽至網站，然後依照指示為您選擇適當的案例。
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>測試外部使用者連線時的考慮事項

針對外部使用者存取的任何測試，都必須包含您組織所支援的每一種內部使用者類型，其中可能包含下列任何或所有專案：
  
- 至少一個同盟網域中的使用者 (我們建議您在) 進行測試。
    
- 匿名使用者。
    
- 組織中從遠端登入商務用 Skype 但不會使用 VPN 的使用者。
    
這些測試會判斷您的 Edge Server 是否為：
  
- 使用網路外部的 telnet 用戶端聆聽必要的連接埠。
    
  - 例如： telnet sip.contoso.com 443
    
  - 您應該在 Edge Server 或 Edge Server 集區上，根據您的部署，對您所使用的埠執行上述測試。
    
- 執行準確的外部 DNS 解析。
    
  - 從您的網路外部，ping Edge Server 或 Edge Server 集區的每個外部 Fqdn。 即使 ping 失敗，您也會看到 IP 位址，您可以比較先前指派的 IP 位址。
    

