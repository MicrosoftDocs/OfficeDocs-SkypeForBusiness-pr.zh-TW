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
description: 通話系統使用者的撥入和撥出通話，可以使用稱為 CallLineIdentity 的原則來控制來電者識別碼。
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660959"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在貴組織中使用來電顯示

來電者識別碼包含兩個使用者對應的資訊：

-  (稱為 CLID 或電話線路識別碼的電話號碼) 。 這是公用交換電話網路 (PSTN) 號碼，顯示為來電者的身分識別。

- 通話方名稱 (通常稱為 CNAM) 。 
  
無論 [PSTN 連線選項](pstn-connectivity.md)為何，所有電話系統使用者都能使用本機號碼器識別碼功能：Microsoft 通話方案、電信業者連線或直接路由。 
  
您可以使用稱為 CallLineIdentity 的原則，控制撥入和撥出電話的來電號碼。 如需詳細資訊，請參閱 [電話線識別碼和通話方名的詳細資訊](more-about-calling-line-id-and-calling-party-name.md)。

  
## <a name="outbound-pstn-caller-id"></a>輸出 PSTN 來電者識別碼

針對輸出 PSTN 來電者識別碼，下列選項可供使用。 
  
- 指派給使用者的電話號碼是預設值。

- 匿名，可透過移除使用者 PSTN 號碼的簡報來取得。 

- 替代電話號碼，可以是：

  - 在 [通話方案] 電話號碼庫存中，將電話號碼分類為服務和免付費電話號碼。 系統會指派給 Teams 自動語音應答或通話佇列。

  - 透過直接路由指派給 Teams 自動語音應答或通話佇列使用的資源帳戶的內部部署電話號碼。 

- 輸出 PSTN 通話的通話方名或 CNAM 設定。  
    
如需詳細資訊，請參閱 [設定使用者的來電識別碼](./set-the-caller-id-for-a-user.md)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>輸出來電識別碼的使用者控制

使用者可以設定 EnableUserOverride 屬性，將來電者識別碼設定變更為 **匿名** 。 

如果輸出來電者識別碼設為匿名，EnableUserOverride 並不會生效，而且來電者識別碼一律設定為匿名。 EnableUserOverride 的預設值為 False。

您的使用者可以將來電者識別碼設定為匿名，方法是移至 [ **設定>通話**]，然後在 [ **來電者標識** 符] 底下，針對 **所有通話選取 [隱藏我的電話號碼和設定檔資訊]**。 此設定變更需要幾分鐘的時間，才能反映新的通話。 

### <a name="notes"></a>注釋

請記住下列事項：

- 您無法為輸出來電者識別碼指派下列類型的電話號碼：

  - 在 [通話方案] 電話號碼清查中分類為使用者的任何電話號碼。

  - 任何透過直接路由指派給使用者的內部部署電話號碼。

  - 商務用 Skype Server內部部署電話號碼。

- 資源帳戶電話號碼替代適用于 Teams 使用者。 服務電話號碼的替代適用于 Teams 使用者。

- 通話方名會在來電時傳送，其中來電者識別碼會以 LineUri、服務或資源帳戶電話號碼取代，以及當來電者是 Teams 使用者時。

- 通話方名最多可以有 200 個字元，但下層系統可能支援較少的字元。

- 若是直接路由，電話號碼替代和通話方名稱會在 FROM SIP 標頭中傳送。 如果對應的 OnlinePstnGateway 設定為 ForwardPai = True，P-PRECISEED-IDENTITY SIP 標頭會包含真正的通話使用者。

- EnableUserOverride 的優先順序高於原則中的其他設定，除非替代設定為匿名。 例如，假設原則實例使用資源帳戶取代，且 EnableUserOverride 是由使用者設定並啟用。 在此情況下，會封鎖輸出來電者識別碼，並使用匿名。 如果原則實例的替代設定為匿名，且 EnableUserOverride 已設定，則無論使用者設定為何，輸出來電者識別碼永遠都是匿名的。

   
## <a name="inbound-caller-id"></a>輸入來電者識別碼

[電話系統] 會將內送外部電話號碼顯示為來電者識別碼。 如果該號碼與 Azure AD 中的使用者或連絡人或個人連絡人相關聯，則商務用 Skype和 Teams 用戶端會根據該資訊顯示來電者識別碼。 如果電話號碼不在 Azure AD 或個人連絡人中，電話公司提供的顯示名稱如果有可用，就會顯示。

BlockIncomingCallerID 屬性可封鎖 PSTN 來電中的來電者識別碼。 您可以設定此屬性，但使用者無法在使用者設定頁面上使用此屬性。 啟用此設定時，傳入的 PSTN 來電者會顯示為來自匿名。
  
若要封鎖輸入來電者識別碼，請參閱 [設定使用者的來電號碼](./set-the-caller-id-for-a-user.md)。
  
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[通話方案所用的不同電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
