---
title: 商務用 Skype 中的群組通話挑選部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 商務用 Skype Server Enterprise Voice 中的群組通話分揀程式和步驟。
ms.openlocfilehash: 870692b1395d96c75d6d96a5914004a8a95f088a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245777"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>商務用 Skype 中的群組通話挑選部署程式
 
商務用 Skype Server Enterprise Voice 中的群組通話分揀程式和步驟。
  
[群組通話挑選] 可讓使用者從自己的手機接聽來電給他們的同事。 
  
 當您部署企業語音時, 會在前端伺服器或標準版伺服器上自動安裝並啟用群組呼叫拾取所用的元件。 不過, 您必須先使用下列步驟來設定群組呼叫挑選, 才能供使用者使用。
  
**群組呼叫進行挑選部署程式**

|**分**|**步驟**|**必要的群組和角色**|**部署檔**|
|:-----|:-----|:-----|:-----|
|在拓撲中啟用 SEFAUtil 工具|使用新的 CsTrustedApplicationPool Cmdlet 來建立新的受信任的應用程式池。 使用新的 CsTrustedApplication Cmdlet, 將 SEFAUtil 工具指定為受信任的應用程式。 執行 Enable-CsTopology Cmdlet 來啟用拓撲。 如果您還沒有它, 請從這個位置下載 SEFAUtil 工具的商務用 Skype Server 版本, 並將它安裝在您在步驟1中建立的受信任的應用程式池中。 執行此程式以驗證 SEFAUtil 是否正常運作, 只要執行它, 即可在部署中顯示使用者的來電轉接設定。 |RTCUniversalServerAdmins  <br/> |[在商務用 Skype 中部署 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [新-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[新-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [商務用 Skype Server 2015 資源套件工具檔](../../management-tools/resource-kit-tools.md)。 (適用于商務用 Skype Server 您必須使用目前的工具版本, 但是來自 Lync Server 2013 的檔仍適用。)  <br/> |
|在 [呼叫公園軌道軌道] 表格中設定呼叫挑選編號範圍  <br/> |使用**CSCallParkOrbit** Cmdlet, 在 [通話駐留軌道] 表格中建立呼叫挑選編號範圍, 並將 [呼叫拾取] 範圍指派給 type **GroupPickup**。  <br/> 若要與現有的撥號方案進行無縫整合, 數位範圍通常會設定為虛擬延伸區塊。 不支援在 [通話駐留軌道] 表格中, 將直向內撥 (已有) 數位指派為範圍數位。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中建立或修改群組呼叫裝貨號碼範圍](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|指派呼叫挑選號碼給使用者, 並為使用者啟用群組呼叫分揀  <br/> |在 SEFAUtil 資源套件工具中使用/enablegrouppickup 參數, 以啟用群組通話分揀, 並為使用者指派呼叫挑選號碼。  <br/> |-  <br/> |[在商務用 Skype 中為使用者啟用群組呼叫挑選並指派群組號碼](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知使用者已指派的電話提貨號碼和任何其他感興趣的號碼  <br/> |在您為使用者啟用群組呼叫挑選之後, 請使用電子郵件或其他機制來通知使用者他們的通話挑選群組號碼。 針對任何您可能想要監視的群組, 將 [呼叫挑選] 群組號碼通知給使用者。 因為使用者可以為其他使用者檢索來電, 即使他們不在同一個群組中, 使用者可能需要多個群組的呼叫挑選群組號碼。  <br/> |-  <br/> ||
|驗證您的群組呼叫裝貨部署  <br/> | 測試放及檢索通話, 以確保您的設定如預期的那樣正常運作。 至少請確認下列事項: <br/>  呼叫已啟用 [群組呼叫] 的使用者, 並讓另一個使用者取回通話。 其他使用者可以位於同一個群組、不同的群組中, 或未啟用 [群組呼叫挑選]。 <br/>  呼叫已啟用 [群組通話] 的使用者, 但不要接聽通話。 <br/> |-  <br/> ||
   

