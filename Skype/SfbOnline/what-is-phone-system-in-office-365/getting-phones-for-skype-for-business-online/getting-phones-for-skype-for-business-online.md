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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: '瞭解哪些電話可商務用 Skype Polycom、HP 和 Mitel 的手機，以及所需的授權。 '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013147"
---
# <a name="getting-phones-for-skype-for-business-online"></a>取得商務用 Skype Online 的電話

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

商務用 Skype線上可針對想要擁有傳統電話體驗，而非使用傳統手機應用程式的使用者，商務用 Skype電話。 本主題涵蓋支援在 商務用 Skype Online 中使用的電話和固件版本，以及當您在組織中設定電話時可協助您的其他資訊。

> [!NOTE]
> Skype商務用將慢慢被 Microsoft Teams 取代為主要通訊Microsoft 365 Office 365。  請參閱[智慧型通訊的新](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/)願景Office 365以進一Office 365瞭解詳細資訊。
>
>若要在支援的裝置上取得最新更新和最新資訊，請參閱智慧Microsoft Teams[裝置。](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>支援的手機
  
Microsoft 正與 Polycom、Yealink 和 AudioCodes 密切合作，透過合作夥伴 IP 電話 計畫 (PIP) 開發及認證各種裝置電話系統。
  
在訂購新的手機商務用 Skype，購買產品識別碼正確的 *電話非常重要*。 這些產品的 ID 可確保您收到的電話已安裝商務用 Skype線上合格版本。
  
|電話夥伴  |商務用 Skype特定產品識別碼  |
|:-----|:-----|
|Polycom   |產品識別碼 -019   |
|Yealink   |SIP-TXXG 商務用 Skype版本   |
|音訊代碼   |UCXXXHDEG (SfB)    |
   
有關 Polycom 電話的詳細資訊，請參閱 [Poly 文件庫](https://documents.polycom.com/category/voice)。
  
有關 Yealink 電話的詳細資訊，請參閱 IP 電話商務用 Skype [>](http://www.yealink.com/products_list_10.html#filter2)。
  
有關 AudioCodes 電話的詳細資訊，請參閱 IP 電話[商務用 Skype>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。
  
> [!NOTE]
> Lync 電話 Online 支援 Lync 商務用 Skype版本，但不支援 Microsoft Teams。 LPE 平臺的主流支援已于 2014 年 4 月 10 日結束，並延長支援直到 2023 年 4 月 11 日，以配合 Lync Server 2013 的產品支援週期。 請參閱 [Microsoft 產品生命週期](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) 以瞭解有關 LPE 生命週期的詳細資訊。 線上版不支援 LPE CAP 商務用 Skype型號。
>
> 今年稍後，Office 365不支援任何 1.2 以前的 TLS 版本。 由於 LPE 的基礎作業系統不支援 TLS 1.2，因此不再支援 LPE Office 365連結。 請參閱[準備在 Office 365 中強制使用 TLS 1.2](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365)以瞭解更多資訊。
  
## <a name="supported-firmware"></a>支援的固件

這是支援電話使用手機所需的最低電話系統：
  

|電話類型 |最小固件 |發行日期 |
|:-----|:-----|:-----|
|優化的 Lync (版電話版本)    |4.0.7577.4463   |2015 年 5 月   |
|通過認證的 Polycom VVX 系列   |5.4.0A   |2015 年 12 月   |
|Yealink   |X.8.1.52   |2017 年 2 月   |
|AudioCodes   |3.0.0.459.1   |2016 年 12 月   |

有關目前通過認證的固件版本的詳細資訊，請參閱[IP 電話商務用 Skype>](../../../SfbPartnerCertification/certification/devices-ip-phones.md)。

> [!NOTE]
> Lync 電話版本 (LPE) 電話您為內部部署所設定，必須先更新至最低或更新必要的固件，再將這些使用者移往 商務用 Skype Online。 如果您在更新手機上的商務用 Skype，將使用者從內部部署移至 商務用 Skype Online，這些電話將無法連線到 商務用 Skype Online。 
  
## <a name="required-licenses"></a>必要的授權

商務用 Skype除了使用者授權外，Online 不需要任何其他 Microsoft 授權。 若要深入瞭解所需的使用者授權，請參閱[商務用 Skype Microsoft Teams附加元件授權](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
  
製造商授權模式可能會因開啟 SIP 和已認證商務用 Skype而有所差異。 如果您是使用 Open SIP 固件重新調整認證模型用途，您必須向製造商驗證固件授權需求。
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>商務用 Skype連線的線上電話功能集

有關完整的裝置功能，請查看製造商的使用者指南。
  

|功能  |Polycom 3PIP  |Yealink 3PIP |AudioCodes 3PIP |LPE |
|:-----|:-----|:-----|:-----|:-----|
|使用使用者認證來登錄   |是  |是   |是   |否   |
|請透過電腦 (配對) Windows   |是   |是   |是   |是   |
|使用網頁 (登錄)   <br/>  <br/> **注意：** 檢查部署指南中的可支援性矩陣。  |是   |是   |是   |否   |
|單鍵加入會議   |是   |是   |是   |是   |
|按一下以撥號 ([配對)    |是   |是   |是   |是> |
|會議控制項   |是   |是   |是   |是   |
|視覺語音信箱   |是   |是   |是   |是   |
|電話鎖   |是   |是   |是   |是   |
|裝置更新   |是   |是   |是   |是   |
|帶內資源配置   |是   |是   |是   |是   |
|QoE   |是   |是   |是   |否  |
|記錄Upload  <br/> <br/> **注意：** 目前，所有記錄只會上傳到 Microsoft 支援小組;目前還無法取得客戶對電話記錄的存取權限。           |是   |是   |是   |是   |
|新式驗證   |是   |是   |是   |否   |
|多個緊急號碼   |是   |否   |否   |是   |
|Exchange日曆整合*   |是   |是   |是   |是  <br/> <br/> **注意：** 需要電腦系系           |
|目前狀態整合   |是   |是   |是   |是   |
|公司目錄   |是   |是   |是   |是   |
|委派   |是   |是   |是   |否   |
|連絡人圖片整合   |否   |是  |否   |是   |


     
> [!NOTE]
> CX 600 或其他 Aries 手機不支援 MFA (多重要素) 。 如果您強制 MFA，這些裝置將無法登錄。 這些裝置只能使用組織識別碼才能使用。
 
## <a name="what-else-should-you-know"></a>您還需要知道什麼？
有關逐步設定指示，請參閱[在線上電話商務用 Skype部署](deploying-skype-for-business-online-phones.md)。

## <a name="related-topics"></a>相關主題
[取得商務用 Skype 和 Microsoft Teams 的服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[以下是可透過電話系統獲得的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[音訊會議與通話方案的適用國家/地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
