---
title: 如何在貴組織中使用來電顯示
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 電話系統使用者可以使用稱為 CallingLineIdentity 原則，同時控制電話系統使用者的來電和外接來電。
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120674"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在貴組織中使用來電顯示

電話系統使用者可以使用稱為 CallingLineIdentity 原則，同時控制電話系統使用者的來電和外接來電。
  
不論 PSTN 連線性如何，所有電話系統使用者都可以使用本機號碼功能：

- Microsoft 通話方案 

- 電話系統直接路由 
  
- 線上 PSTN 連線
    
- 使用商務用 Skype 雲端連接器版本 (內部部署 PSTN 連接需要雲端連接器版本 1.4.2 及) 
    
- 內部部署 PSTN 連接與商務用 Skype Server (需要商務用 Skype Server 2015 CU5 及更新版本) 
    
> [!NOTE]
> 此政策不適用於商務用 Skype 2015 Server。 
  
## <a name="outbound-caller-id"></a>外發本機號碼

有三個選項可用於外發 PSTN 本機號碼：
  
- 指派給使用者的電話號碼，這是預設值。
    
- 在通話方案電話號碼庫存中歸類為服務和免付費號碼的電話號碼。 它通常會指派給組織自動電話機或通話佇列。
    
- 設為匿名。
    
不過，您無法為外發本機號碼指派以下類型的電話號碼：
  
- 在通話方案電話號碼庫存中歸類為使用者的任何電話號碼
    
- 商務用 Skype Server 內部部署電話號碼
    
若要設定外發本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>使用者對外發本機號碼控制項

EnableUserOverride 屬性可讓單一或多個使用者將本機號碼設定變更為 **匿名**。 只有在使用 LineURI 或 Substitute 的 CallingIDSubstitute 參數設定 CallingLineIdentity 原則時，才適用此設定。 EnableUserOverride 的預設值為 False。
  
您的使用者可以使用商務用 Skype 桌面用戶端中的設定選項卡，將本機號碼設為匿名，選取系統管理員 **)** 啟用的呼叫使用者 (，然後選取隱藏所有通話的電話號碼和設定檔 **資訊**。 在 Teams 中，使用者可以前往右上角的個人資料圖片，選取設定通話，然後在呼叫者識別碼下，選取隱藏所有通話的電話號碼和設定檔  >  ******資訊**。 
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**版本** <br/> |**支援** <br/> |
|按一下以執行  <br/> |目前通道于 2016 年 12 月 6 日發行 - 版本 1611 (7571.2072)   <br/> |是  <br/> |
|按一下以執行  <br/> |2017 年 2 月 22 日發行的第一次延遲通道版本 - 版本 1701 (版本 7766.2060)   <br/> |是  <br/> |
|按一下以執行  <br/> |延後通道于 2017 年 6 月 13 日發行 - 版本 1701 (版本 7766.2092)   <br/> |是  <br/> |
|微星  <br/> |商務用 Skype  <br/> |否  <br/> |
|Mac  <br/> |商務用 Skype  <br/> |否  <br/> |
   
## <a name="inbound-caller-id"></a>本機號碼

如果號碼與 Azure AD 中的使用者相關聯，電話系統會顯示外部電話號碼的已呼叫識別碼。 如果電話號碼不在 Azure AD 中，則如果可用，就會顯示由電信公司提供的顯示名稱。

BlockIncomingCallerID 屬性可讓您封鎖傳入 PSTN 通話的本機號碼。 您可以設定此屬性，但使用者設定頁面上的使用者無法使用此屬性。 目前僅適用于線上 PSTN 連線。
  
若要設定外發本機號碼，請參閱[設定使用者的本機號碼。](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>相關主題
[移轉電話號碼的常見問題](./phone-number-calling-plans/port-order-overview.md)

[用於通話方案的各種電話號碼](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款及條件](./emergency-calling-terms-and-conditions.md)

[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
