---
title: 取得商務用 Skype Online 的電話
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
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: '瞭解哪些電話可與 Polycom、HP 和 Mitel 的商務用 Skype 一起使用，以及所需的授權。 '
ms.openlocfilehash: 03f9a6d5cf3ac496c4828825e68f068ec98a14ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106439"
---
# <a name="getting-phones-for-skype-for-business-online"></a>取得商務用 Skype Online 的電話

商務用 Skype Online 可針對想要擁有傳統電話體驗，而非使用商務用 Skype 應用程式的使用者，提供桌面電話的資格和支援。 本主題涵蓋商務用 Skype Online 中支援的電話和固件版本，以及當您在組織中設定電話時可協助您的其他資訊。

> [!NOTE]
> 商務用 Skype 將會慢慢被 Microsoft Teams 取代為 Microsoft 365 和 Office 365 的主要通訊方式。  請參閱 [Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) 智慧型通訊的新願景以瞭解更多資訊。
>
>若要在支援的裝置上取得最新更新和最新資訊，請參閱適用于智慧通訊的 Microsoft [Teams 裝置](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。
  
## <a name="supported-phones"></a>支援的手機
  
Microsoft 正與 Polycom、Yealink 和 AudioCodes 密切合作，透過電話系統的合作夥伴 IP 電話計畫 (PIP) 開發及認證各種裝置。
  
訂購商務用 Skype 的新電話時，購買產品識別碼正確的 *電話非常重要*。 這些產品的 ID 可確保您收到的電話已安裝商務用 Skype Online 合格版本。
  
|||
|:-----|:-----|
|**電話合作夥伴** <br/> |**商務用 Skype 特定產品識別碼** <br/> |
|Polycom  <br/> |產品識別碼 -019  <br/> |
|Yealink  <br/> |SIP-TXXG 商務用 Skype Edition  <br/> |
|音訊代碼  <br/> |UCXXXHDEG (SfB)   <br/> |
   
有關 Polycom 電話的詳細資訊，請參閱 [Poly 文件庫](https://documents.polycom.com/category/voice)。
  
有關 Yealink 電話的詳細資訊，請參閱 [商務用 Skype IP 電話](http://www.yealink.com/products_list_10.html#filter2)。
  
有關 AudioCodes 電話的詳細資訊，請參閱 [商務用 Skype IP 電話](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync Phone Edition 受商務用 Skype Online 支援，但 Microsoft Teams 不支援。 LPE 平臺的主流支援已于 2014 年 4 月 10 日結束，並延長支援直到 2023 年 4 月 11 日，以配合 Lync Server 2013 的產品支援週期。 請參閱 [Microsoft 產品生命週期](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) 以瞭解有關 LPE 生命週期的詳細資訊。 商務用 Skype Online 不支援 LPE CAP 模型。
>
> 今年稍後，Office 365 不支援任何 1.2 以前的 TLS 版本。 由於 LPE 的基礎作業系統不支援 TLS 1.2，因此不再支援 LPE 連接到 Office 365。 請參閱 [準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) 以瞭解更多資訊。
  
## <a name="supported-firmware"></a>支援的固件

這是支援電話使用電話系統所需的最低軟體版本：
  
||||
|:-----|:-----|:-----|
|**電話類型** <br/> |**最小固件** <br/> |**發行日期** <br/> |
|Lync Phone Edition (優化)   <br/> |4.0.7577.4463  <br/> |2015 年 5 月  <br/> |
|通過認證的 Polycom VVX 系列  <br/> |5.4.0A  <br/> |2015 年 12 月  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |2017 年 2 月  <br/> |
|音訊代碼  <br/> |3.0.0.459.1  <br/> |2016 年 12 月  <br/> |

有關目前通過認證的固件版本的詳細資訊，請參閱 [商務用 Skype IP 電話](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

> [!NOTE]
> Lync Phone Edition (LPE) 您為內部部署所設定的電話，必須先更新為最低或更新必要的固件，才能將這些使用者移往商務用 Skype Online。 如果您在更新手機上的固件之前，先將使用者從內部部署移至商務用 Skype Online，這些電話將無法連線到商務用 Skype Online。 
  
## <a name="required-licenses"></a>必要的授權

商務用 Skype Online 不需要使用者授權外的其他 Microsoft 授權。 若要深入瞭解所需的使用者授權，請參閱商務用 Skype 和 [Microsoft Teams 附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
開啟的 SIP 和商務用 Skype 認證固件之間，製造商授權模式可能會有所不同。 如果您是使用 Open SIP 固件重新調整認證模型用途，您必須向製造商驗證固件授權需求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>商務用 Skype Online 連線電話功能集

有關完整的裝置功能，請查看製造商的使用者指南。
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**功能** <br/> |**Polycom 3PIP** <br/> |**Yealink 3PIP** <br/> |**音訊代碼 3PIP** <br/> |**LPE** <br/> |
|使用使用者認證來登錄  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|透過 PC 帳戶 (配對) ，僅適用于 Windows  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|使用網頁 (帳戶)   <br/>  <br/> **注意：** 檢查部署指南中的可支援性矩陣。           |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|單鍵加入會議  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|按一下以撥號 ([配對)   <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|會議控制項  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|視覺語音信箱  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|電話鎖定  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|裝置更新  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|帶內資源調配  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|QoE  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|記錄上傳  <br/> <br/> **注意：** 目前，所有記錄只會上傳到 Microsoft 支援小組;目前還無法取得客戶對電話記錄的存取權限。           |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|新式驗證  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|多個緊急號碼  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |
|Exchange 日曆整合*  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> <br/> **注意：** 需要電腦系系           |
|目前狀態整合  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|公司目錄  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |
|委派  <br/> |是  <br/> |是  <br/> |是  <br/> |否  <br/> |
|連絡人圖片整合  <br/> |否  <br/> |是  <br/> |否  <br/> |是  <br/> |
||||||

     
> [!NOTE]
> CX 600 或其他 Aries 手機不支援 MFA (多重要素) 。 如果您強制 MFA，這些裝置將無法登錄。 這些裝置只能使用組織識別碼才能使用。
 
## <a name="what-else-should-you-know"></a>您還需要知道什麼？
有關逐步設定指示，請參閱部署商務用 [Skype Online 電話](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相關主題
[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[以下是可透過電話系統獲得的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音訊會議與通話方案的適用國家/地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
