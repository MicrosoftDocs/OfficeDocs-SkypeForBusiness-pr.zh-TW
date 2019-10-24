---
title: 在商務用 Skype Online 中取得電話
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '從 Polycom、HP 和 Mitel，以及所需的授權，瞭解哪些手機可搭配商務用 Skype 使用。 '
ms.openlocfilehash: ac3b262a9888acb95eef4e2e8822abc3441617c4
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "37642490"
---
# <a name="getting-phones-for-skype-for-business-online"></a>在商務用 Skype Online 中取得電話

商務用 skype Online 可為想要取得傳統電話經驗的使用者（而不是使用商務用 Skype 應用程式）提供和支援桌面電話。 本主題涵蓋在商務用 Skype Online 中支援使用的電話和固件版本，以及當您在組織中設定手機時可協助您的其他資訊。

> [!NOTE]
> 在 Office 365 中，商務用 Skype 將會以 Microsoft 團隊的主要通訊方式來取代。  如需詳細資訊，請參閱[Office 365 中適用于智慧通訊的新構想](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/)。
>
>若要取得最新的更新以及支援的裝置上的最新資訊，請參閱[適用于智慧通訊的 Microsoft 團隊裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。
  
## <a name="supported-phones"></a>支援的電話
  
Microsoft 是與 Polycom、Yealink 和 AudioCodes 密切合作與共同作業，透過 Office 365 和商務用 Skype Server 中的 [合作夥伴 IP 電話] 程式（PIP）來開發及認證各種裝置。
  
針對商務用 Skype 排序新電話時，請務必購買擁有*正確產品識別碼*的手機。 這些產品識別碼可確保您收到的手機已安裝商務用 Skype Online 的合格版本。
  
|||
|:-----|:-----|
|**電話合作夥伴** <br/> |**商務用 Skype 特定產品識別碼** <br/> |
|Polycom  <br/> |產品識別碼-019  <br/> |
|Yealink  <br/> |SIP-TXXG 商務用 Skype 版本  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
如需有關 Polycom 手機的詳細資訊，請參閱[Microsoft 的語音方案](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。
  
如需有關 Yealink 手機的詳細資訊，請參閱[商務用 SKYPE IP 電話](http://www.yealink.com/products_list_10.html#filter2)。
  
如需有關 AudioCodes 手機的詳細資訊，請參閱[商務用 SKYPE IP 電話](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync Phone Edition 支援商務用 Skype Online，但不適用於 Microsoft 團隊。 LPW 平臺的主流支援已于4月/10/2014 年結束，延伸支援直到2013年4月/11/2023 年與 Lync Server 的產品支援週期相符。 如需 LPW 生命週期的詳細資訊，請參閱[Microsoft 產品生命週期](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO)。 商務用 Skype Online 不支援 LPW CAP 模型。
>
> 今年之後，Office 365 將不支援任何版本低於1.2 的 TLS。 因為 LPW 基礎作業系統不支援 TLS 1.2，所以 LPW 將不會受到支援，因此無法連線至 Office 365。 如需詳細資訊，請參閱[準備 Office 365 中的 TLS 1.2 的強制使用](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="supported-firmware"></a>支援的固件

這是支援的電話在 Office 365 中搭配手機系統使用所需的最低軟體發行：
  
||||
|:-----|:-----|:-----|
|**電話類型** <br/> |**最低固件** <br/> |**發行日期** <br/> |
|已優化（Lync 手機版）  <br/> |4.0.7577.4463  <br/> |2015年5月  <br/> |
|已驗證的 Polycom VVX 系列  <br/> |5.4。0  <br/> |2015年12月  <br/> |
|Yealink  <br/> |X.x.x.x 8.1.52  <br/> |2017年2月  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |2016年12月  <br/> |

如需目前認證的固件版本的詳細資訊，請參閱[商務用 SKYPE IP 電話](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones)。

> [!NOTE]
> 在將這些使用者移至商務用 Skype Online 之前，您在內部部署中設定的 Lync Phone Edition （LPW）手機必須更新為最低或較新的所需固件。 如果您在更新手機上的固件前將使用者從內部部署移至商務用 Skype Online，則這些手機將無法連線至商務用 Skype Online。 
  
## <a name="required-licenses"></a>所需的授權

商務用 Skype Online 不需要使用者授權以外的任何其他 Microsoft 授權。 若要深入瞭解所需的使用者授權，請參閱[商務用 Skype 和 Microsoft 團隊附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
[製造商授權模型] 可能會因開啟的 SIP 與商務用 Skype 認證固件而有所不同。 如果您要使用開啟的 SIP 固件來重新調整認證模型的用途，您必須與製造商驗證固件授權需求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>已設定商務用 Skype Online 的手機功能集

如需完整裝置功能與功能，請參閱製造商使用者指南。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**功能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**AudioCodes 3PIP** <br/> |**LPW** <br/> |
|使用使用者認證登入  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |不  <br/> |
|透過電腦（配對）登入，僅限 Windows  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|使用登入（網頁登入）  <br/>  <br/> **注意：** 檢查 [部署指南] 中的 [支援清單]。           |是的  <br/> |是的  <br/> |是的  <br/> |不  <br/> |
|按一下 [加入會議]  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|按一下撥打（配對）  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|會議控制項  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|視覺語音信箱  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|電話鎖定  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|裝置更新  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|頻帶內配  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|QoE  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |不  <br/> |
|記錄上傳  <br/> <br/> **注意：** 目前，所有的記錄都只會上傳到 Microsoft 支援小組;客戶無法存取手機記錄。           |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|新式驗證  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |不  <br/> |
|多個緊急號碼  <br/> |是的  <br/> |不  <br/> |不  <br/> |是的  <br/> |
|Exchange 行事曆整合 *  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> <br/> **注意：** 需要電腦 tethering           |
|目前狀態整合  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|公司目錄  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |
|委派  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |不  <br/> |
|連絡人圖片整合  <br/> |不  <br/> |是的  <br/> |不  <br/> |是的  <br/> |
||||||

     
> [!NOTE]
> CX 600 或任何其他 Aries 手機不支援多重要素驗證（MFA）。 如果您強制進行 MFA，這些裝置將無法登入。 這些裝置必須只使用組織識別碼來進行 authetication。
 
## <a name="what-else-should-you-know"></a>您還應該知道什麼？
如需逐步設定指示，請參閱[部署商務用 Skype Online 手機](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相關主題
[取得商務用 Skype 和 Microsoft 團隊的服務電話號碼](../getting-service-phone-numbers.md)

[以下是您在 Office 365 中使用電話系統所取得的結果](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[適用于音訊會議與通話方案的國家和地區可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
