---
title: 商務用 Skype 中群組呼叫裝貨的部署程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: 商務用 Skype Server 企業語音中群組通話挑選的部署程式與步驟。
ms.openlocfilehash: bd3f299e8121483cf8a6a7b332c806923a386c66
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601918"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>商務用 Skype 中群組呼叫裝貨的部署程式
 
商務用 Skype Server 企業語音中群組通話挑選的部署程式與步驟。
  
群組叫用收取可讓使用者從自己的電話接聽來電給其同事。 
  
 當您部署企業語音時，會自動在前端伺服器或 Standard Edition Server 上安裝及啟用群組呼叫收取所使用的元件。 不過，您必須使用下列步驟來設定群組呼叫收取，使用者才能使用它。
  
**群組呼叫收取部署程式**

|**階段**|**步驟**|**所需群組和角色**|**部署文件**|
|:-----|:-----|:-----|:-----|
|在拓撲中啟用 SEFAUtil 工具|使用 New-CsTrustedApplicationPool Cmdlet 來建立新的受信任應用程式集區。 使用 New-CsTrustedApplication Cmdlet，將 SEFAUtil 工具指定為信任的應用程式。 執行 Enable-CsTopology Cmdlet 以啟用拓撲。 若尚未使用此位置，請從這個位置下載 SEFAUtil 工具的商務用 Skype Server 版本，然後將它安裝在您在步驟1中建立的信任應用程式集區。 執行該 SEFAUtil 以在部署中顯示使用者的「來電轉接」設定，以確認是否正常運作。 |RTCUniversalServerAdmins  <br/> |[在商務用 Skype 中部署 SEFAUtil 工具](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [商務用 Skype Server 2015 資源套件工具檔](../../management-tools/resource-kit-tools.md)。 商務用 Skype Server 的 (您必須使用目前的工具版本，但是來自 Lync Server 2013 的檔仍適用。 )   <br/> |
|設定通話駐留軌道表格中的呼叫收取號碼範圍  <br/> |使用 **New-CSCallParkOrbit** Cmdlet 來建立通話駐留軌道表格中的呼叫收取號碼範圍，並將類型 **GroupPickup** 指派給電話收取範圍。  <br/> 為了與現有撥號對應表無縫整合，號碼範圍通常會設定為虛擬擴充區塊。 指派直接向內撥號 (，不支援通話駐留軌道表格中的範圍編號) 數位。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[在商務用 Skype 中建立或修改群組呼叫收取號碼範圍](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|將來電收取號碼指派給使用者，並為使用者啟用群組呼叫收取功能  <br/> |使用 SEFAUtil resource 成套工具中的/enablegrouppickup 參數，啟用群組呼叫收取，並為使用者指派呼叫收取號碼。  <br/> |-  <br/> |[在商務用 Skype 中為使用者啟用群組呼叫收取和指派群組號碼](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|通知使用者他們所指派的來電收取號碼和其他相關數目  <br/> |在您為使用者啟用群組呼叫收取後，請使用電子郵件或其他一些機制通知使用者他們的呼叫收取群組號碼。 通知使用者他們可能想要監視的任何群組的呼叫收取群組號碼。 因為使用者可以為其他使用者取回來電，即使這些使用者不在相同的群組中，使用者可能需要多個群組的呼叫收取群組號碼。  <br/> |-  <br/> ||
|驗證群組是否呼叫收取部署  <br/> | 測試放入和取回通話，以確保您的設定如預期般運作。 請至少確認下列專案： <br/>  呼叫為群組呼叫收取啟用的使用者，並讓另一位使用者取回通話。 另一個使用者可以位於相同的群組中，也可以位於不同的群組中，或是未啟用群組呼叫收取。 <br/>  呼叫已啟用群組呼叫收取的使用者，且不接聽通話。 <br/> |-  <br/> ||
