---
title: 如何在貴組織中使用來電顯示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 本機號碼功能可以使用稱為 CallingLineIdentity 電話系統，同時控制使用者的來電和外電話系統來電。
ms.openlocfilehash: 97070be995d56451a7b6b1969c8d3751ebaaffe5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624605"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在貴組織中使用來電顯示

本機號碼包含兩個使用者可辨識的資訊：

- 電話號碼 (稱為 CLID 或電話線識別碼) 。 這是以來電者 (PSTN) 的公用切換電話號碼。

- 通話方名稱 (通常稱為 CNAM) 。 
  
無論 PSTN 連接選項如何，電話系統使用者都可以使用本機號碼功能：

- Microsoft 通話方案 

- 電話系統直接路由 
  
您可以使用稱為 CallingLineIdentity 原則來控制來電和來電的本機號碼。 詳細資訊，請參閱[更多通話線路識別碼和通話方名稱。](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>外發 PSTN 本機號碼

針對外發 PSTN 本機號碼，提供下列選項。 
  
- 指派給使用者的電話號碼，這是預設值。

- 匿名，可移除使用者的 PSTN 號碼簡報。 

- 替代電話號碼，可以是：

  - 在通話方案電話號碼庫存中歸類為服務和免付費號碼的電話號碼。 它通常會指派給自動Teams或通話佇列。

  - 內部部署電話號碼，透過直接路由指派給自動Teams或通話佇列使用的資源帳戶。 

- 外發 PSTN 通話上的通話方名稱或 CNAM 設定。  
    
詳細資訊，請參閱設定使用者的[本機號碼。](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>使用者對外發本機號碼控制項

使用者可以設定 EnableUserOverride 屬性，將本機號碼設定變更為匿名。  

如果外發本機號碼設為匿名，則 EnableUserOverride 沒有作用，且本機號碼一直設為匿名。 EnableUserOverride 的預設值為 False。

您的使用者可以將來電設為匿名 **，設定 >** 來電，然後在呼叫者識別碼下，選取隱藏所有通話的電話號碼和設定檔 **資訊**。

### <a name="notes"></a>注釋

請記住下列事項：

- 您無法為外發本機號碼指派下列類型的電話號碼：

  - 在通話方案電話號碼庫存中歸類為使用者的任何電話號碼。

  - 透過直接路由指派給使用者的任何內部部署電話號碼。

  - 內部商務用 Skype Server電話號碼。

- 資源帳戶電話號碼替代的使用僅適用于Teams使用者。 服務電話號碼的取代適用于線上商務用 Skype使用者Teams電話號碼。

- 通話方名稱只會在來電中以 LineUri、服務或資源帳戶電話號碼取代來電，以及當來電者是Teams使用者時。

- 通話方名稱最多可以有 200 個字元，但下游系統可能支援較少的字元。

- 針對直接路由，電話號碼取代和通話方名稱會以 FROM SIP 標頭傳送。 如果對應的 OnlinePstnGateway 是使用 ForwardPai = True 進行配置，則 P-IDENTITY-IDENTITY SIP 標頭會包含真正的通話使用者。

- EnableUserOverride 優先于原則中的其他設定，除非替代設定為匿名。 例如，假設原則實例使用資源帳戶進行取代，且使用者已設定並啟用 EnableUserOverride。 在這種情況下，會封鎖外發本機號碼，且會使用匿名。 如果原則實例的取代設定為匿名，且 EnableUserOverride 已設定，則無論使用者設定如何，出站本機號碼一直是匿名。

   
## <a name="inbound-caller-id"></a>本機號碼

電話系統本機號碼外部電話號碼。 如果號碼與 Azure AD 中的使用者或連絡人或個人連絡人相關聯，商務用 Skype Teams用戶端就會根據該資訊顯示本機號碼。 如果電話號碼不在 Azure AD 或個人連絡人中，如果可用，就會顯示由電信公司提供的顯示名稱。

BlockIncomingCallerID 屬性可讓您封鎖傳入 PSTN 通話的本機號碼。 您可以設定此屬性，但使用者設定頁面上的使用者無法使用此屬性。 啟用此設定時，內建 PSTN 來電者會顯示為來自匿名。
  
若要封鎖輸入本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
