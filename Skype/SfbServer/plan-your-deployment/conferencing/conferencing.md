---
title: 在商務用 Skype Server 中規劃會議
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 中的會議功能和功能。
ms.openlocfilehash: 669c87bd2c5eae3944a586e289bbeac3fd4409df
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394985"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃會議
 
**總結：** 閱讀此主題以瞭解商務用 Skype Server 中的會議功能和功能。
  
商務用 Skype Server 中的會議可讓使用者使用商務用 Skype 用戶端來開會和保持會議，而不是每個人都在相同的聊天室中取得。 會議參與者可以使用其商務用 Skype 用戶端來連線至會議，以取得完整的音訊和影片體驗，或是使用電話撥入會議。 會議也支援立即訊息、桌面和應用程式共用，以及互動的白板。
  
本主題包含下列各節：
  
- 會議功能及功能
    
- 會議元件
    
- 會議原則
    
- 大型會議的支援
    
- 決定組織的需求
    
## <a name="conferencing-features-and-capabilities"></a>會議功能及功能

商務用 Skype Server 有四種會議類型： web 會議、音訊和影片 (A/V) 會議、電話撥入式會議和立即訊息 (IM) 會議。 
  
您可以選擇啟用所有會議類型，或根據您的需求，只使用一種類型。 例如，您可以啟用所有類型（包括撥入式會議），以允許無法使用商務用 Skype 用戶端加入會議的使用者，撥打並參與來自電話的會議音訊。 當您部署商務用 Skype Server 時，會自動部署 IM 會議功能; 您可以使用拓撲產生器，指定是否要部署 web、A/V 和電話撥入式會議。 如需詳細資訊，請參閱[商務用 Skype Server 中的部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。 
  
下列小節說明每種會議類型的特性和功能。
  
### <a name="web-conferencing"></a>Web 會議

Web 會議可讓會議出席者在會議期間共用的檔上進行共同作業，而會議簡報者則可以透過商務用 Skype 用戶端來共用應用程式。 Web 會議提供下列功能： 
  
- **白板和批註。** 白板是空白的畫布，可以藉由文字、手寫、繪圖和影像來進行共同作業。 在白板上所做的註釋，所有會議參與者都看得到。 白板功能透過讓會議參與者討論構想、激發靈感、摘記等等，進而增強了共同作業。
    
- **投票。** 輪詢功能可讓簡報者快速判斷參與者的喜好設定，以改善共同作業。 線上會議和交談期間，簡報者可以使用輪詢來收集參與者的匿名回應。 所有簡報者都可以看到結果，也可以對全部出席者隱藏或顯示結果。
    
- **應用程式共用和桌面共用。** 在會議期間，會議簡報者可以在多部監視器環境中共用其整個桌面、個別應用程式或個別監視器。 除了只查看內容之外，會議中的其他參與者也可以要求對簡報者的畫面進行控制，並透過許可權與內容 (（包括滾動及編輯) ）進行互動。 會議參與者也可以做為簡報者，並在會議期間開始共用內容。
    
- **PowerPoint 共用。** 可讓使用者透過 Office Web Apps 伺服器共用會議中 PowerPoint 簡報，以供：
    
  - 高解析度顯示及支援 PowerPoint 功能，例如動畫、投影片切換效果及內嵌影片。
    
  - 行動裝置可以存取這些簡報。
    
  - 具有適當許可權的使用者可以獨立于簡報本身在 PowerPoint 簡報中向外移動。 例如，當 Ken 展示其投影片放映時，Heidi 可以查看任何想要的投影片，而不會影響 Ken 的簡報。
    
### <a name="audio-and-video-conferencing"></a>音訊和影片會議

音訊和影片會議可用於會議中的音訊和影片。 音訊允許出席者相互交談，就好像他們在相同的聊天室。 影片會在以支援影片的網路攝像機或會議裝置加入會議的任何出席者或簡報者的商務用 Skype 用戶端中，啟用影片顯示。
  
 商務用 Skype Server 提供數種功能，讓使用者可用來為使用者設定語音會議體驗，包括下列專案：
  
- **物件靜音。** 簡報者可以使用此設定來靜音會議中所有的音訊參與者，並將會議置於非簡報者無法自行取消靜音的狀態。
    
- **會議進入/出口宣告。** 如果您已啟用電話撥入式會議，簡報者可以使用此設定開啟或關閉進入和關閉宣告，以在會議進行中時，將干擾減至最小。
    
- **以撥號方式新增使用者。** 簡報者和授與出席者的許可權，可將 PSTN 號碼新增至會議，並讓會議撥出至這些號碼。
    
  商務用 Skype Server 提供數種功能，讓使用者可用來為使用者設定影片會議體驗，包括下列專案：
  
- **圖庫 View。** 在包含超過兩個人的影片會議中，使用者會自動查看會議中的所有人。 如果會議的參與者超過五位，則最活躍的參與者影片會出現在頂端列，而只有照片顯示給其他參與者。 預設會開啟多方影片。
    
- **全景影片。** 如果在會議室中安裝 RoundTable 的視訊會議裝置，這項功能會提供會議室的完整360度視圖。 只有 RoundTable 裝置可以使用全景影片帶。
    
- **僅限簡報者影片模式。** 簡報者可以設定會議，只顯示簡報者的影片。 這會在多個視頻資料流程可供使用，並且鎖定于不同來源時，防止大型會議中的干擾。 這種模式也適用于 RoundTable 裝置所捕捉及提供的影片。
    
- **影片聚光燈。** 簡報者可以設定會議，使會議中的其他參與者只會看到來自選取之參加影片來源之參與者的影片。 這種模式也適用于透過顯示全景影片 RoundTable 裝置所捕獲並提供的影片。
    
### <a name="dial-in-conferencing"></a>電話撥入式會議

電話撥入式會議可讓會議出席者使用電話撥入會議以加入會議的音訊部分。 電話撥入式會議是音訊會議的子集，並且需要額外設定。 如需電話撥入式會議的詳細資訊，請參閱[在商務用 Skype Server 中規劃商務用 Skype Server 中的電話撥](dial-in-conferencing.md)入式會議，以及[設定中的電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。 
  
### <a name="instant-messaging-conferencing"></a>立即訊息會議

立即訊息 (IM) 會議可允許兩方雙方在單一 IM 會話中進行通訊。 如需 IM 會議的詳細資訊，請參閱[在商務用 Skype Server 中規劃立即訊息和目前狀態](../../plan-your-deployment/instant-messaging-and-presence.md)。
  
## <a name="conferencing-components"></a>會議元件

支援會議功能的元件包括下列各項：
  
- **Application service。** Application service 提供一個平臺，用以部署、主控和管理整合通訊 (UC) 應用程式。 電話撥入式會議使用需要 Application service 的兩個 UC 應用程式：會議語音應答和會議宣告。 預設會在前端集區中的每一部前端伺服器上安裝並啟用應用程式服務。 它也會安裝在每一部 Standard Edition 伺服器上，以啟用及設定電話撥入式會議。
    
- **會議語音應答應用程式。** 會議語音應答應用程式是一種整合通訊應用程式，可接受公用交換電話網路 (PSTN) 通話、播放提示，以及將通話加入 A/V 會議。 當您啟用電話撥入式會議時，預設會安裝及啟用會議語音應答應用程式。
    
- **會議宣告應用程式。** 會議宣告應用程式是一種整合通訊應用程式，可針對特定動作播放色調和提示，例如當參與者加入或離開會議時，參與者會靜音或 unmuted、某人進入會議會議廳，或是鎖定或解除鎖定會議。 會議宣告應用程式也支援來自電話鍵區的雙音調多頻率 (DTMF) 命令。 當您啟用電話撥入式會議時，預設會自動安裝並啟用會議宣告應用程式。
    
- **電話撥入式會議設定] 頁面。** [電話撥入式會議設定] 頁面會顯示會議撥入號碼，其可用的語言、指派的會議資訊 (也就是不需要排程) 的會議，以及在會議 DTMF 控制項中，且支援管理個人識別碼 (PIN) 並指派會議資訊。 [電話撥入式會議設定] 頁面會自動安裝為 Web 服務的一部分。
    
- **轉送伺服器和 PSTN 閘道。** 電話撥入式會議需要一台轉送伺服器，以商務用 Skype Server 與 pstn 閘道之間的某些設定) 來轉譯信令 (和媒體，以及在轉送伺服器和 pstn 閘道之間轉譯信號和媒體的 PSTN 閘道。 若為電話撥入式會議，您必須至少部署一個轉送伺服器，至少要有下列其中一項：
    
  - PSTN 閘道
    
  - IP-PBX
    
  - 透過設定 SIP 主幹) 所連接的網際網路電話語音服務提供者 (SBC)  (的會話邊界控制器
    
  > [!NOTE]
  > 如果您也部署企業語音，轉送伺服器和 PSTN 閘道是企業語音部署的一部分。 如果您不是部署企業語音，您必須至少部署一個轉送伺服器，以及至少一個 PSTN 閘道、IP-PBX 或 SBC 用於電話撥入式會議。 
  
- **檔存放區。** 檔存放區用於記錄的名稱音訊檔。 檔存放區是每 Enterprise Edition 或 Standard Edition 部署中的標準元件。
    
- **使用者存放區。** 使用者存放區用於儲存使用者商務用 Skype Server pin。 會散列 Pin。 使用者存放區是每 Enterprise Edition 或 Standard Edition 部署中的標準元件。
    
- **Office Web Apps Server。** 若要使用 web 會議功能，管理員必須安裝 Office web apps server，而且必須設定商務用 Skype Server 以與 Office web apps server 通訊。
    
## <a name="conferencing-policies"></a>會議原則

若要強制執行組織的原則及控制頻寬使用量，您可以設定使用者可以組織之會議類型的原則。 您可以定義各種各樣的會議原則，並將它們指派給個別使用者和使用者群組。 您也可以設定管理對等交談的原則。 如需設定會議原則的詳細資訊，請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。 如需頻寬管理的詳細資訊，請參閱[在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
## <a name="support-for-large-meetings"></a>大型會議的支援

商務用 Skype Server 所能支援的會議大小，取決於會議是否主控于共用或專屬集區：
  
- 在共用集區上，商務用 Skype Server 可以主控最多250個使用者的會議。 共用集區是主控所有商務用 Skype Server 工作負載的集區，包括立即訊息 (IM) 和顯示狀態、會議及企業語音。 
    
- 在專屬集區上，商務用 Skype Server 可以使用 web 和音訊/視頻 (A/V) 會議（包括共用 PowerPoint 簡報），支援最多1000位參與者的會議。 此支援需要設定為支援大型會議和管理的專屬集區，其方式是可確保一次只主控一項大型會議。 
    
如需管理大型會議的詳細資訊，請參閱[在商務用 Skype Server 中規劃大型會議](large-meetings.md)。
  
如果您的組織需要較大的會議能力，您應該考慮採用 Skype 會議廣播的混合式環境，該 Office 365 屬於 Microsoft 365 和的線上服務。 Skype 會議廣播可讓使用者主控及廣播會議至最多10000參與者的大型線上受眾。 使用 Skype 會議廣播必須已在具有實際 Microsoft 365 或 Office 365 組織的混合式設定中設定商務用 Skype Server。 所有使用者都必須以必要條件建立線上承租人。 如果您想要部署可利用 Skype 會議廣播的混合式解決方案，請參閱[設定內部部署以取得 Skype 會議廣播](../../deploy/configure-skype-meeting-broadcast.md)。
  
## <a name="determine-your-organizations-needs"></a>決定組織的需求

您在決定要部署哪些會議功能時，需要考量要提供給使用者的功能，以及網路頻寬功能。 下列清單會引導您完成會議規劃程式，以根據組織的需求來判斷應部署的會議功能。
  
> [!NOTE]
> 當您在部署時啟用會議時，會自動啟用 web 和 A/V 會議。 不過，您可以依照本主題先前所述的方式來設定會議原則，以停用特定的功能。 
  
- **您想要啟用 Web 會議功能，並納入文件共同作業及應用程式共用功能嗎？**
    
    如果是的話，您必須使用規劃工具或使用拓撲產生器，為前端集區啟用會議。 如需詳細資訊，請參閱[商務用 Skype Server 中的部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    應用程式共用功能需要使用比文件共同作業更多的網路頻寬。 商務用 Skype Server 提供節流機制來控制每個應用程式共用會話。 預設會將每一個工作階段的節流機制設為 1.5 KB/秒。 如果您不想啟用應用程式共用，但想要檔共同作業，您可以啟用會議及使用會議原則來停用應用程式共用。 如需設定會議原則的詳細資訊，請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。
    
    若要讓使用者能夠共用 PowerPoint 簡報，您必須設定 Office Web Apps Server。 如需設定 Office 網頁應用程式伺服器的詳細資訊，請參閱[在商務用 Skype Server 中設定 Office Web apps server 的整合](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **您是否要啟用音訊和視訊會議？**
    
    如果是的話，您必須使用規劃工具或使用拓撲產生器，為前端集區啟用會議。 如需詳細資訊，請參閱[商務用 Skype Server 中的部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。
    
    音訊和影片會議需要和使用的網路頻寬超過 web 會議 (，包括檔共同作業和應用程式共用) 。 如果您不想啟用音訊和視訊會議，但想要啟用 web 會議，可以啟用會議和使用會議原則來停用 A/V 會議。
    
    如果您想要啟用音訊會議，而不是影片會議，您可以啟用 A/V 會議，並使用會議原則來阻止影片會議。 或者，您可以啟用 A/V 會議功能並僅允許特定使用者啟動或參與 A/V 會議。 
    
    如需設定會議原則的詳細資訊，請參閱[在商務用 Skype Server 中管理會議原則](../../manage/conferencing/conferencing-policies.md)。
    
    > [!NOTE]
    > 您不需要企業語音即可使用 A/V 會議。 若您啟用 A/V 會議功能，即使您的電話解決方案使用 PBX，使用者只要有音訊裝置，就可以在會議中新增音訊。 
  
- **您想要讓使用 PSTN 電話的使用者加入會議的音訊部分嗎？**
    
    如果是的話，請部署並啟用電話撥入式會議功能。這時，來自組織內外的受邀使用者就可以透過 PSTN 電話加入會議的音訊部分。
    
    電話撥入式會議是一種選用的功能，您可以在部署商務用 Skype Server 會議時加以設定。 雖然電話撥入式會議使用企業語音所使用的部分相同元件，但即使您未部署企業語音，也可以部署電話撥入式會議。 電話撥入式會議同時支援企業和匿名使用者。 如需設定適用于企業和匿名使用者之電話撥入式會議的詳細資訊，請參閱商務用 Skype Server 中的[部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)及[設定商務用 Skype Server 中的電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md)。
    
- **您是否要讓具有商務用 Skype 用戶端的外部使用者加入會議？**
    
    透過允許外部參與會議，您可以在商務用 Skype Server 中達到最大的投資。 外部使用者包括：
    
  - **遠端使用者。** 組織本身的使用者，當他們在防火牆外工作時，使用其膝上型電腦或其他商務用 Skype Server 裝置。
    
  - **同盟使用者。** 公司的使用者也可以使用商務用 Skype Server 的使用者。 為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。
    
  - **匿名使用者。** 由您的使用者特別邀請加入特定會議的其他所有外部使用者。 公司裡的會議召集人可以將會議的電子郵件邀請寄送給外部使用者。 該電子郵件內含一則連結，外部使用者只需要點選一下即可加入會議。
    
    如果您想要允許外部使用者，您需要部署 Edge Server。 此外，部署 Edge Server 之後，您可以建立與其他組織的同盟關係，例如，您的客戶或廠商--以及這些組織的使用者可以更輕鬆地與您的使用者共同作業。
    
    如需部署 Edge Server 的詳細資訊，請參閱 Plan for Edge Servers 及 Deploy Edge Servers。 如需啟用 Office Web apps server 的外部存取的詳細資訊，請參閱[在商務用 Skype Server 中設定 Office Web apps server 的整合](../../deploy/deploy-conferencing/office-web-app-server.md)。
    
- **您想要控制可加入商務用 Skype Server 會議的用戶端嗎？**
    
    如果是的話，請設定 [會議加入] 頁面，限制您想要支援的用戶端選項。 每當使用者按一下連結加入排程會議時，商務用 Skype Server 會偵測電腦上是否已安裝用戶端。 這時，它會啟動預設的用戶端並開啟 [會議加入] 頁面，其中包含其他用戶端的連結。 [會議加入] 頁面一定會包含使用商務用 Skype Web 應用程式的選項。 除了此選項之外，您還可以決定是否要包含出席者和舊版 Communicator 的連結。 
    

