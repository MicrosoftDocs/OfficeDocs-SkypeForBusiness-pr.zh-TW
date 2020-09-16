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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解功能、可用性，以及如何規劃及設定商務用 Microsoft Phone 系統。 '
ms.openlocfilehash: 32c094860ee5ff102a541062616e038cf2f37be6
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820567"
---
# <a name="heres-what-you-get-with-phone-system"></a>以下是可透過電話系統獲得的功能

本文將說明電話系統功能。 如需使用電話系統作為私人分支 Exchange 的詳細資訊 (PBX) 取代，以及連線到公開交換電話網絡 (PSTN) 的選項，請參閱 [什麼是電話系統](what-is-phone-system-in-office-365.md)。

用戶端可在 PC、Mac 和行動裝置上使用，它可提供從平板電腦和手機到 Pc 和桌面 IP 手機的裝置功能。 如需詳細資訊，請參閱 [取得 Microsoft 團隊的用戶端](get-clients.md)。

 > [!Note]
> 如需不同平臺上的小組電話系統的詳細資料，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  
## <a name="phone-system-features"></a>電話系統功能

[電話系統] 提供下列功能。 除非另有說明，否則在團隊和商務用 Skype Online 中都有提供功能。
  
|||
|:-----|:-----|
|**電話系統功能** <br/> |**描述** <br/> |
|[雲端自動語音應答](what-are-phone-system-auto-attendants.md) <br/> |可讓您建立可讓外部與內部呼叫者找到並將來電放入或轉接給貴組織中的公司使用者或部門的功能表系統。  <br/> |
|[雲端通話佇列](create-a-phone-system-call-queue.md) <br/> |可讓您設定為貴組織管理呼叫佇列的方式：例如，[保留問候語]、[暫留音樂]、[搜尋下一個可用的通話代理程式] 來處理通話，依此類推。  <br/> |
|等候音樂 | 當從公用交換電話網絡 (PSTN) 的外部呼叫保留時，會播放服務所定義的預設音樂。 除了呼叫佇列撥打電話之外，此功能也適用于一對一的 PSTN 對團隊通話。 這項功能可提供與其他平臺的保留期間通知同位。 此功能可由系統管理員進行設定，但 [目前只能透過 PowerShell](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)進行設定。 在 PSTN 通話的諮詢式轉接中，也不支援等候音樂。|
|依名稱和編號呼叫應答/啟動 ()   <br/> |讓使用者以觸控方式接聽來電，並撥打完整的電話號碼或按一下用戶端中的名稱，以進行撥出通話。  <br/> |
|[來電轉接選項和同時撥打](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) <br/> |讓使用者設定轉寄規則，讓通話在任何地方都能使用，或者來電可以轉寄給同事或語音信箱。  <br/> |
|[[群組通話] 和 [轉寄至] 群組](call-sharing-and-group-call-pickup.md) <br/> | 讓使用者與同事共用來電，讓同事接聽在使用者無法使用時所發生的通話。 對收件者的中斷會比其他通話共用 (（例如來電轉接或同時撥打) ），因為使用者可以設定接收撥入式共用通話的方式。 |
|[轉接通話與顧問式轉接](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> |讓使用者將來電轉接給其他人。 或者，如果他們需要離開自己的 office，但想要繼續交談，他們可以將呼叫從他們的 PC 或 IP 手機轉接到他們的手機。  <br/> |
|[轉接至語音信箱 mid 通話](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0) <br/> | 讓使用者在通話期間轉移至語音信箱。 |
|[通話駐留和擷取](call-park-and-retrieve.md)  <br/> | 讓使用者在雲端的 [小組服務] 中保留通話。 當通話停用時，服務會產生唯一的呼叫檢索程式碼。 停用通話的使用者，或其他人可以使用該程式碼和支援的 app 或裝置來檢索通話。 <br/> |
|從搜尋撥打電話號碼  <br/> | 讓使用者使用/call 命令並指定名稱或數位，在搜尋方塊中放置通話。 <br/> |
|[來電顯示](how-can-caller-id-be-used-in-your-organization.md)  <br/> |從公司內部進行通話會顯示詳細的本機號碼，該識別碼會從公司目錄提取資訊，並顯示圖片識別碼和工作標題，而不只是電話號碼。 對於來自外部電話號碼的呼叫，會顯示電話服務提供者所提供的本機號碼。 如果外部電話號碼是企業目錄中的次要號碼，則會顯示來自企業目錄的資訊。  <br/> |
|裝置切換  <br/> |讓使用者在與小組連接的另一個 HID 裝置上，玩通話或會議;例如，從電腦喇叭切換至耳機。   <br/> |
|目前狀態式呼叫路由 <br/> |控制與目前狀態的入站通訊，讓使用者封鎖所有傳入通訊，除了特別指出的以外。  <br/> |
|[整合式撥號鍵台](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89) <br/> | 讓使用者在搜尋列和撥號鍵台中的任何位置以名稱或按號碼撥號，以加速撥出電話的程式。 <br/> |
|聯盟通話  <br/> |讓使用者能夠與同盟租使用者安全地連線、溝通及共同作業。  <br/> |
|[撥打及接聽視頻通話](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42) <br/> | 如果使用者的帳戶已啟用視頻通話，則使用者可以與連絡人進行面對面的視頻通話。 他們需要的是相機、電腦的喇叭和麥克風。 如果使用者的電腦沒有內建的音訊裝置，也可以使用耳機。<br/> |
|[雲端語音信箱](set-up-phone-system-voicemail.md) <br/> | 當使用者收到語音信箱時，會以電子郵件的形式傳送給其 Exchange 信箱，並將語音信箱訊息做為附件。 使用者可以在其認證的桌面手機，以及所有團隊或商務用 Skype 應用程式上聽取他們的訊息。 已新增到2017年3月的語音信箱支援，且預設為所有組織和使用者啟用。   <br/> |
|[雲端語音信箱使用者設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 讓使用者為語音信箱問候語設定用戶端設定、呼叫應答規則及問候語言，包括外出問候語。   |
|[副鈴聲](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) <br/> | 已將多個喇叭裝置連接至其電腦的使用者，可以選擇將次要裝置設定為除了預設的喇叭之外進行響鈴。 例如，當有耳機連接至 PC 和書桌喇叭的使用者，您可以選擇在撥打電話時同時撥打耳機和辦公桌喇叭，以免來電。  |
|僅限 (團隊的[特殊鈴聲通知](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)) <br/> |讓使用者為一般通話、轉寄通話和委派通話選擇不同的鈴聲，讓他們可以區別通話類型。  <br/> |
|[共用線路外觀](shared-line-appearance.md) <br/> | 讓使用者共用自己的電話線路，讓其他使用者代表自己撥打及接聽來電。|
|[繁忙 (團隊](teams-calling-policy.md) 只能)  <br/> | 通話原則可讓您設定當使用者已在通話或會議中，或有保留的通話時處理來電的方式。 來電者在手機上時，來電者會聽到占線信號。 被呼叫者會收到未接來電通知，但無法接聽來電。 預設會停用此功能，但租使用者管理員可以開啟此功能。 |
|[通話封鎖](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US) <br/> | 讓使用者將 (PSTN) 電話號碼新增到封鎖的清單，讓該號碼的下一個呼叫封鎖給使用者。|
|[常見的區域電話](set-up-common-area-phones.md) <br/> | 常見的區域手機通常位於大廳或會議室等區域，讓多人都能使用。 常見的區域手機是設定為裝置，而不是使用者，而且可以自動登入網路。|
|[媒體略過支援](direct-routing-plan-media-bypass.md) (僅限團隊直接傳送)  <br/> | 若要取得較佳的效能，媒體會保留在會話邊界控制器 (SBC) 與用戶端，而不是透過 Microsoft Phone 系統傳送。 |


## <a name="availability-in-gcc-high-and-dod-clouds"></a>在 GCC 高和 DoD 雲彩中的可用性
<a name="bkmk_setup"> </a>

在 GCC 高和 DoD 雲彩中尚不提供下列功能。 
- [副鈴聲、語音信箱和增強式委派的通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [轉接至語音信箱 mid 通話](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 從搜尋列撥打電話號碼
- 等候音樂
- Azure AD 反向號碼查閱

## <a name="related-topics"></a>相關主題

- [什麼是電話系統](what-is-phone-system-in-office-365.md)
- [Microsoft Teams 的雲端語音](cloud-voice-landing-page.md)
- [設定電話系統](setting-up-your-phone-system.md)
- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [電話系統直接路由](direct-routing-landing-page.md)
- [監控及管理通話品質](monitor-call-quality-qos.md)
- [Microsoft Teams 附加元件授權](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [電話系統的定價](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [使用 callings 與會議的虛擬化桌面基礎結構團隊](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)

  
 
