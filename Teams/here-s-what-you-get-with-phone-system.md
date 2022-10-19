---
title: 以下是可透過電話系統獲得的功能
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
msreviewer: jastarck, roykuntz
ms.topic: conceptual
ms.assetid: bc9756d1-8a2f-42c4-98f6-afb17c29231c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '瞭解功能、可用性，以及如何為您的企業規劃和設定 Microsoft Phone System。 '
ms.openlocfilehash: ccc931bd15e511903715ca328a142eb4da313dea
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584784"
---
# <a name="heres-what-you-get-with-phone-system"></a>以下是可透過電話系統獲得的功能

本文將說明電話系統功能。 如需使用電話系統做為私人交換 (PBX) 取代的詳細資訊，以及連線到公用交換電話網路 (PSTN) 的選項，請參閱 [什麼是電話系統](what-is-phone-system-in-office-365.md)。

用戶端適用于 PC、Mac 和行動裝置，可在裝置上提供從平板電腦、行動電話到電腦和桌面 IP 手機等功能。 如需詳細資訊，請參閱 [取得 Microsoft Teams 的用戶端](get-clients.md)。

 > [!Note]
> 如需不同平臺上 Teams 手機系統的詳細資訊，請參閱 [各平臺的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

若要使用電話系統功能，您的組織必須具備電話系統授權。 如需授權的詳細資訊，請參閱 [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

請注意，大部分的功能都需要您指派電話系統授權，並確保使用者「已啟用語音」。 若要指派授權，請使用 [Set-CsPhoneNumberAssignment Cmdlet](/powershell/module/teams/set-csphonenumberassignment?view=teams-ps) ，並將 **EnterpriseVoiceEnabled** 參數設為$true。 雲端自動語音應答等一些功能不需要使用者的語音功能。 下表會標出例外狀況。
  
## <a name="phone-system-features"></a>電話系統功能

電話系統提供下列功能。
  
|電話系統功能  |描述 |
|:-----|:-----|
|[雲端自動語音應答](what-are-phone-system-auto-attendants.md)  |可讓您建立功能表系統，讓外部和內部來電者找出並撥打或轉接電話給公司使用者或貴組織中的部門。  <br/> 請注意，使用者 *不需要* 具備語音功能，即可依名稱從自動語音應答撥號接聽來電，可依號碼目錄搜尋來撥號。 使用者 *必須* 具備語音功能，才能從自動語音應答功能表選項接聽來電。 |
|[雲端通話佇列](create-a-phone-system-call-queue.md) <br> |可讓您設定組織管理通話佇列的方式：例如，設定問候語和音樂保留、搜尋下一個可用的來電專員來處理通話等等。  <br/> 請注意，使用者 *必須* 具備語音功能，才能從通話佇列接聽來電。|
|[等候音樂](music-on-hold.md) | 當來自公用交換電話網路 (PSTN) 的外部通話處於保留狀態時，播放由服務定義的預設音樂，或由租使用者系統管理員上傳的自訂音樂。 除了撥打到通話佇列的通話之外，此功能適用于一對一 PSTN 對 Teams 通話。 此功能提供保留通知與其他平臺的同位。 |
|以名稱和號碼) 接聽電話/起始 (   |可讓使用者輕觸一下接聽輸入電話，並透過撥打完整電話號碼或按一下用戶端中的名稱來撥打撥出電話。   |
|[來電轉接選項和同時撥打](https://support.office.com/article/call-forwarding-call-groups-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)  |讓使用者設定轉接規則，讓通話可以隨處移動，或將電話轉接給同事或語音信箱。   |
|[群組通話接聽和轉接到群組](call-sharing-and-group-call-pickup.md)  | 讓使用者與同事共用來電，讓同事可以接聽使用者無法接聽的電話。 與其他形式的通話共用 (，例如來電轉接或同時撥打) ，對收件者干擾較小，因為使用者可以設定收到共用來電通知的方式。 |
|[轉接電話和轉接電話](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  |讓使用者將電話轉接給其他人。 或者，如果他們需要離開辦公室，但想要繼續交談，他們可以將電話從電腦或 IP 電話轉接到行動電話。  <br/> 請注意，使用者 *不需要* 具備語音功能，就能接聽其他使用者轉接的電話。 |
|[轉接至語音信箱中電話*](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)  | 可讓使用者在通話期間轉接至語音信箱。 |
|[通話駐留和擷取](call-park-and-retrieve.md)   | 讓使用者在雲端的 Teams 服務中保留通話。 當通話停駐時，服務會產生唯一的呼叫擷取代碼。 停用通話的使用者或其他使用者就可以使用該代碼以及支援的應用程式或裝置來擷取通話。  |
|從搜尋撥打電話號碼   | 讓使用者使用 /call 命令並指定名稱或號碼，從搜尋方塊撥打電話。  |
|[來電顯示](how-can-caller-id-be-used-in-your-organization.md)   |公司內部的來電會顯示詳細的來電識別碼，從公司目錄提取資訊，顯示圖片識別碼和職稱，而不只是電話號碼。 如果是來自外部電話號碼的來電，則會顯示電話服務提供者提供的來電者識別碼。 如果外部電話號碼是公司目錄中的次要號碼，則會顯示公司目錄中的資訊。   |
|裝置切換   |讓使用者在連線至 Teams 的另一部 HID 裝置上進行通話或會議;例如，從電腦喇叭切換到耳機。    |
|目前狀態型通話路由  |控制目前狀態的輸入通訊，讓使用者封鎖所有內送通訊，但特定指示的通訊除外。   |
|[整合式撥號鍵台](https://support.office.com/article/use-the-dial-pad-in-teams-27bc60b5-74c0-4e9c-808b-da4db9514d89)  | 可讓使用者在搜尋列和撥號鍵台中的任何位置，依名稱或號碼撥號，加快撥出電話的程式。  |
|同盟通話   |讓使用者安全地與同盟租使用者中的使用者聯繫、通訊及共同作業。   |
|[撥打和接聽視訊通話](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)  | 如果使用者的帳戶已啟用視訊通話，使用者可以與連絡人進行面對面視訊通話。 他們只需要相機、電腦的喇叭和麥克風。 如果使用者的電腦沒有內建音訊裝置，也可以使用耳機。 |
|[雲端語音信箱](set-up-phone-system-voicemail.md)  | 當使用者收到語音信箱時，語音信箱會以電子郵件的形式傳送至其 Exchange 信箱，並以語音信箱訊息做為附件。 使用者可以在經認證的桌面手機，以及所有 Teams 或商務用 Skype應用程式上聆聽訊息。 自 2017 年 3 月起，已新增語音信箱轉譯的支援，並預設會針對所有組織和使用者啟用。 <br> 請注意，使用者 *不需要* 電話系統授權，*也* 不需要語音功能才能使用雲端語音信箱功能。    |
|[雲端語音信箱使用者設定](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 讓使用者設定其用戶端設定語音信箱問候語、通話接聽規則和問候語，包括不在辦公室問候語。 <br> 請注意，使用者 *不需要* 電話系統授權，*也* 不需要語音功能才能使用雲端語音信箱功能。  |
|[次要響鈴](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)  | 連線至電腦的多個喇叭裝置的使用者，除了預設喇叭之外，還可以選擇設定次要裝置響鈴。 例如，將耳機連接到電腦和桌面喇叭的使用者可以選擇在來電時讓耳機和桌上喇叭同時響鈴，這樣他們就不會錯過通話。  |
|僅限 Teams () [的特殊響鈴通知](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f) |讓使用者選擇一般通話、轉接電話及委派通話的個別鈴聲，以便區分通話類型。   |
|[共用線路外觀](shared-line-appearance.md)  | 讓使用者共用電話線，讓其他使用者可以代表他們撥打和接聽電話。|
|[只) 在 [忙碌] (Teams 上忙碌](teams-calling-policy.md)  | 通話原則可讓您設定當使用者接聽來電時的處理方式： <ul><li>在通話中 </li><li>在會議中</li><li>保留通話。 </li></ul> 來電者會收到下列其中一個回應： <ul><li>當來電者正在使用電話時，會聽到忙碌訊號</li> <li>將會路由到使用者的未回答設定。 其中一個選項可讓來電者為已在通話中的使用者留下語音信箱。</li></ul> 來電者收到未接來電通知，但無法接聽來電。 此功能預設為停用，但可以由租使用者系統管理員開啟。|
|[通話封鎖](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f?ui=en-US&rs=en-US&ad=US)  | 讓使用者將 (PSTN) 電話號碼新增至封鎖清單，如此一來，該號碼的下一個通話便無法讓使用者響鈴。|
|[常見區域電話](set-up-common-area-phones.md)  | 常見的區域電話通常會放在大廳或會議室等區域，供多人使用。 常見的區域電話設定為裝置而非使用者，而且可以自動登入網路。|
|僅限 Teams 直接路由的[媒體略過支援](direct-routing-plan-media-bypass.md) ()   | 為了獲得更好的效能，媒體會保留在會話框線控制器 (SBC) 和用戶端之間，而不是透過電話系統傳送。 |
|[未指派的號碼路由](routing-calls-to-unassigned-numbers.md) | 允許將未指派的號碼路由傳送給使用者、自動語音應答、通話佇列或自訂公告。 |

## <a name="availability-in-gcc-high-and-dod-clouds"></a>GCC High 和 DoD 雲中的可用性
<a name="bkmk_setup"> </a>

GCC High 和 DoD Clouds 尚未提供下列功能。 

- [次要響鈴、語音信箱和增強委派的通話設定](https://support.office.com/article/Manage-your-call-settings-in-Teams-456cb611-3477-496f-b31a-6ab752a7595f)
- [轉接至語音信箱中電話](https://support.office.com/article/Transfer-a-call-in-Teams-b7f40f14-e083-46b9-b739-68038c8f73a0)
- 從搜尋列撥打電話號碼
- 等候音樂
- Azure AD 反向數位查閱

## <a name="related-topics"></a>相關主題

- [什麼是電話系統](what-is-phone-system-in-office-365.md)
- [Microsoft Teams 的雲端語音](cloud-voice-landing-page.md)
- [設定電話系統](setting-up-your-phone-system.md)
- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [監控及管理通話品質](monitor-call-quality-qos.md)
- [Microsoft Teams 附加元件授權](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [電話系統的定價](https://products.office.com/microsoft-teams/voice-calling#requirements)
- [含通話和會議的虛擬化桌面基礎結構 Teams](teams-for-vdi.md#teams-on-vdi-with-calling-and-meetings)
