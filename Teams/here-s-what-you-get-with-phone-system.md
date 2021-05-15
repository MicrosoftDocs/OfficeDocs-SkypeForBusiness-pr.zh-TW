---
title: 以下是可透過電話系統獲得的功能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, makolomi
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解功能、可用性，以及如何規劃及設定適用于Microsoft 電話系統。 '
ms.openlocfilehash: 2d4f4bada45242ddd5a3aa48308d2acaad495a23
ms.sourcegitcommit: a628b22c9a0ef3bcd7dee3f308a79b4c427872cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2021
ms.locfileid: "52491773"
---
# <a name="heres-what-you-get-with-phone-system"></a>以下是可透過電話系統獲得的功能

本文將說明電話系統功能。 有關使用 電話系統 做為私人分支 Exchange (PBX) 更換，以及連接至公用交換電話網絡 (PSTN) 選項的詳細資訊，請參閱什麼是[電話系統。](what-is-phone-system-in-office-365.md)

用戶端適用于 PC、Mac 和行動裝置，可在平板電腦、行動電話、PC 和桌面 IP 電話等裝置上提供功能。 詳細資訊，請參閱取得[用戶端Microsoft Teams。](get-clients.md)

 > [!Note]
> 有關在不同平臺上Teams電話系統的詳細資訊，請參閱[Teams平臺的功能。](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)
  
## <a name="phone-system-features"></a>電話系統功能

電話系統提供下列功能。 除非另有說明，否則功能可在線上Teams商務用 Skype使用。
  
|||
|:-----|:-----|
|**電話系統功能** <br/> |**描述** <br/> |
|[雲端自動話務員](what-are-phone-system-auto-attendants.md) <br/> |可讓您建立功能表系統，讓外部和內部來電者能夠找出及撥打或轉接電話給貴組織的公司使用者或部門。  <br/> 請注意， *使用者不需要* 啟用語音功能，就不需要從自動語音機接聽來電。 |
|[雲端通話佇列](create-a-phone-system-call-queue.md) <br> |可讓您設定貴組織的通話佇列管理方式：例如，設定保留問候語和音樂、搜尋下一個可用的通話代理程式來處理通話，等等。  <br/> 請注意， *使用者必須* 啟用語音功能，以從通話佇列接聽來電。|
|等候音樂 | 當從公用交換電話網絡或 PSTN (外部通話置於保留狀態) 服務定義的預設音樂。 此功能適用于一對一 PSTN 對Teams通話，以及通話佇列的通話。 此功能提供與其他平臺的保留通知奇偶性。 此功能是由系統管理員所配置，但目前[僅透過 PowerShell 進行。](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) PSTN 通話的諮詢轉移也不支援等候音樂。|
|按名稱和號碼 (接聽/啟動)   <br/> |讓使用者以觸控功能接聽來電，並撥打完整電話號碼或按一下用戶端中的名稱來撥打撥出電話。  <br/> |
|[呼叫轉譯選項和同時撥打](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |讓使用者設定轉轉規則，讓通話可以隨處進行，或將通話轉轉到同事或語音信箱。  <br/> |
|[群組呼叫代答和轉往群組](call-sharing-and-group-call-pickup.md) <br/> | 讓使用者與同事共用來電，讓同事可以接聽使用者無法使用時發生的通話。 與其他通話共用方式相比 (例如呼叫轉轉或同時撥打) 對收件者的干擾較小，因為使用者可以設定接收來電通知的方式。 |
|[轉接通話和諮詢轉移](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |允許使用者將通話轉接給其他人。 或者，如果他們需要離開辦公室，但想要繼續交談，可以將電話從電腦或 IP 電話轉接到行動電話。  <br/> 請注意， *使用者不需要* 啟用語音功能，就不需要從其他使用者接聽轉接的通話。 |
|[轉接至語音信箱通話*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | 讓使用者在通話期間轉接至語音信箱。 |
|[通話駐留和擷取](call-park-and-retrieve.md)  <br/> | 讓使用者在雲端的 Teams中保留通話。 當通話被停駐時，服務會產生唯一的通話取回程序代碼。 之後，將通話停駐的使用者或其他人就可以使用該程式碼和支援的應用程式或裝置來取回通話。 <br/> |
|從搜尋撥打電話號碼  <br/> | 讓使用者使用 /call 命令，並指定名稱或號碼，從搜尋方塊進行通話。 <br/> |
|[來電顯示](how-can-caller-id-be-used-in-your-organization.md)  <br/> |公司內部的來電會顯示詳細的本機號碼，從公司目錄提取資訊，顯示圖片識別碼和職稱，而不是只顯示電話號碼。 針對來自外部電話號碼的通話，會顯示電話服務提供者提供的本機號碼。 如果外部電話號碼是公司目錄中的次要號碼，則會顯示公司目錄中的資訊。  <br/> |
|裝置切換  <br/> |讓使用者在另一個已連接到該裝置上的 HID 裝置上Teams;例如，從電腦喇叭切換到耳機。   <br/> |
|目前狀態型通話路由 <br/> |使用目前狀態控制輸入通訊，讓使用者封鎖所有傳入通訊，但特定指示除外。  <br/> |
|[整合式撥號鍵台](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | 讓使用者在搜尋欄和撥號鍵台中的任何位置，以名稱或號碼撥號，加快撥出通話程式。 <br/> |
|聯合通話  <br/> |讓使用者安全地與聯盟租使用者中的使用者聯繫、通訊及共同合作。  <br/> |
|[撥打和接收視音訊通話](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | 如果使用者帳戶已啟用視音訊通話功能，使用者可以與連絡人進行面對面視像通話。 他們只需要相機、電腦的喇叭和麥克風。 如果使用者的電腦沒有內建的音訊裝置，也可以使用耳機。<br/> |
|[雲端語音信箱*](set-up-phone-system-voicemail.md) <br/> | 當使用者收到語音信箱時，語音信箱會以電子郵件Exchange以語音信箱訊息作為附件傳送到他們的信箱。 使用者可以在經過認證的桌面電話，以及所有應用程式或Teams商務用 Skype訊息。 自 2017 年 3 月新增語音信箱字幕支援，且所有組織和使用者預設都啟用此功能。   <br/> |
|[雲端語音信箱使用者設定*](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 允許使用者設定語音信箱問候語、通話接聽規則及問候語的用戶端設定，包括公司外問候語。   |
|[次要響鈴](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | 有多個喇叭裝置連接到電腦的使用者除了預設喇叭之外，也可以選擇將次要裝置設為響鈴。 例如，將耳機連接到電腦和桌面喇叭的使用者，可以選擇在來電進入時同時讓耳機和桌面喇叭同時響鈴，這樣他們才能不錯過通話。  |
|[唯一的響](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)鈴 (Teams提醒) <br/> |讓使用者為一般通話、轉呼叫和委派通話選擇不同的鈴聲，以便區別通話類型。  <br/> |
|[共用線路外觀](shared-line-appearance.md) <br/> | 讓使用者共用其電話線，讓其他使用者可以代表他們撥打和接聽電話。|
|[忙碌在忙碌 (Teams](teams-calling-policy.md)只有)  <br/> | 通話政策可讓您設定在使用者時如何處理來電： <ul><li>在通話中 </li><li>在會議</li><li>已保留通話。 </li></ul> 來電者會收到下列其中一個回應： <ul><li>當通話物件在電話上時，聽到忙碌訊號</li> <li>會依此路由至使用者的未解說設定。 其中一個選項可讓來電者為已經在通話中的使用者留下語音信箱。</li></ul> 受話者收到未接來電通知，但無法接聽來電。 此功能預設為停用，但租使用者系統管理員可以開啟此功能。|
|[通話封鎖](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 讓使用者將 (PSTN) PSTN 新) 到封鎖清單中，這樣該號碼的下一個通話就禁止撥打使用者。|
|[一般地區電話](set-up-common-area-phones.md) <br/> | 一般區域電話會放在大廳或會議室等區域，讓多人使用。 一般區域電話會設定為裝置，而不是使用者，而且可以自動登入網路。|
|[媒體旁 (支援](direct-routing-plan-media-bypass.md)Teams直接路由)  <br/> | 為了提升績效，媒體會保留在會話邊界控制器 (SBC) 與用戶端之間，而不是透過 Microsoft 電話 系統傳送。 |


\* 使用者不需要啟用語音信箱功能。

## <a name="availability-in-gcc-high-and-dod-clouds"></a>高GCC DoD 雲端的可用性
<a name="bkmk_setup"> </a>

下列功能尚未在高雲GCC DoD 雲端中提供。 

- [次要鈴聲、語音信箱和增強委派的通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [轉接至語音信箱通話](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 從搜尋欄撥打電話號碼
- 等候音樂
- Azure AD 反向數位尋找

## <a name="related-topics"></a>相關主題

- [什麼是電話系統](what-is-phone-system-in-office-365.md)
- [Microsoft Teams 的雲端語音](cloud-voice-landing-page.md)
- [設定電話系統](setting-up-your-phone-system.md)
- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [電話系統直接路由](direct-routing-landing-page.md)
- [監控及管理通話品質](monitor-call-quality-qos.md)
- [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話系統的定價](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [Teams虛擬桌面基礎結構的通話和會議](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
