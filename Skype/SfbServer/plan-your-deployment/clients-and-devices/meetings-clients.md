---
title: '規劃會議用戶端 (Web 應用程式和會議應用程式) '
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 摘要： IT 專業人員應該在規劃商務用 Skype Server 時，複查商務用 Skype Web 應用程式和 Skype 會議應用程式的支援需求。 本文並非適用于這些應用程式的使用者。
ms.openlocfilehash: bf6eb62291309500c942e83c41e898b5a4d25531
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395155"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>規劃會議用戶端 (Web 應用程式和會議應用程式) 
 
**總結：** IT 專業人員應該在規劃商務用 Skype Server 時，複查商務用 Skype Web 應用程式和 Skype 會議應用程式的支援需求。 本文並非適用于這些應用程式的使用者。
  
一旦您執行商務用 Skype Server，組織的使用者可能會將商務用 Skype 用戶端安裝為部署程式的一部分。 
  
稍後，這些使用者可能會建立會議並邀請來自組織外部的使用者，而這些會議被邀請者可能沒有任何版本的商務用 Skype 用戶端。 當使用者按一下會議邀請的 URL 時，就會偵測到缺少用戶端，而且不會有商務用 Skype 用戶端的被邀請者會要求您下載並安裝輕量、只有會議的用戶端，這樣他們才可以加入會議。
  
> [!NOTE]
> 只有在沒有商務用 Skype 的情況下嘗試登入會議時，才可使用商務用 Skype Web 應用程式和 Skype 會議應用程式。 這些應用程式的使用者説明位於 [https://aka.ms/smahelp](https://aka.ms/smahelp) 。 
  
> [!NOTE]
> 您無法預先安裝商務用 Skype Web 應用程式或 Skype 會議應用程式，但[smart phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1)和[平板](https://products.office.com/skype-for-business/download-app?tab=tabs-2)電腦使用者可能能夠安裝可用於參加會議的廉價行動用戶端。
  
根據預設，主控會議的伺服器會將使用者下載並安裝商務用 Skype Web 應用程式以加入會議。 商務用 Skype Web 應用程式儲存在前端伺服器上，而且會傳送給會議出席者。 
  
針對商務用 Skype Server，Skype 的會議應用程式 (于 Windows) 上，Mac 版商務用 Skype (的 Mac) 可以取代為商務用 Skype Web 應用程式從 CU5 開始的取代，但提供取代應用程式需要所述的其他設定。在 [[啟用 Skype 會議應用程式] 以取代商務用 Skype Web 應用程式 (選用) ](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。 如果已啟用 Skype 會議應用程式和 Mac 版商務用 Skype，使用者將會從 Microsoft 365 或 Office 365 內容傳遞網路下載最新版本的應用程式，而不是從 (伺服器下載 CDN) 。 針對商務用 Skype Server 2019，使用 Skype 會議應用程式和 Mac 版商務用 Skype 是唯一的選項。
  
Skype 會議應用程式提供簡化的瀏覽器體驗，可供下載及安裝應用程式，以及加入會議（包括對 Internet Explorer 使用者的按一下加入）。 Skype 會議應用程式對商務用 Skype Web 應用程式可靠性和會議體驗還有許多改進功能。 
  
> [!NOTE]
> 從商務用 Skype Server 2015 CU5 或更新版本，使用商務用 Skype 線上所用的會議將不再傳送 clientless 使用者您的商務用 Skype Web 應用程式，而是會傳送 Skype 會議應用程式 (Windows) 或 Mac 版商務用 Skype Mac) 上的 (。 從商務用 Skype Server 2015 CU5 或更新版本中，如果您[啟用 Skype 會議應用程式以取代商務用 Skype Web 應用程式 (選用) ](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)，clientless 使用者將會傳送 Skype 會議應用程式或 Mac 版商務用 Skype，而不是商務用 Skype Web 應用程式。 
  
## <a name="software-requirements"></a>軟體需求
<a name="OS-Browser"> </a>

若要使用商務用 Skype Web 應用程式，使用者必須具備下列其中一種支援的作業系統和瀏覽器混合。 
  
**商務用 Skype Web 應用程式的作業系統和最低瀏覽器支援**

| 作業系統 | 銳利 | 32和 64-位 Internet Explorer 11 或更新版本 | 32和 64-位 Internet Explorer 10 或更新版本 | 32和 64-位 Internet Explorer 9 或更新版本 | 32和64位版本的 Safari 6.2.8-11. X | 32和 64-位版本的 Chrome 18. X 或更新版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是  <br/> |是  <br/> |不適用  <br/> |不適用  <br/> |不適用  <br/> |Yes &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |不適用  <br/> |是  <br/> |不適用  <br/> |不適用  <br/> |不適用 <br/> |Yes &#x2778; <br/> |
|Windows 8 (英特爾) &#x2776; <br/> |不適用  <br/> |不適用  <br/> |是  <br/> |不適用 <br/> |不適用  <br/> |Yes &#x2778; <br/> |
|Windows 7，含 SP1 &#x2777; <br/> |不適用  <br/> |是  <br/> |否  <br/> |否  <br/> |無 <br/>|Yes &#x2778; <br/> |
|使用 SP1 Windows Server 2008 R2 &#x2777; <br/> |不適用  <br/> |是  <br/> |是  <br/> |是  <br/> |不適用 <br/>|Yes &#x2778; <br/> |
| (以 Intel 為基礎的) macOS 10.8 和更新版本 &#x2777; <br/> |不適用  <br/> |不適用  <br/> |不適用  <br/> |不適用  <br/> |是  <br/> |是 <br/> |
   
&#x2776; 商務用 Skype Web 應用程式瀏覽器外掛程式需要特定的共用外掛程式，才能使用電腦型語音、影片、共用及查看進行中畫面共用和其他功能。 會議出席者可以選擇在加入會議時安裝共用外掛程式，或在他們啟動這些功能的其中一個。 在 Windows 8 和 Windows 8.1 中，只有當您執行的是桌面的 Internet Explorer 10 或 Internet Explorer 11 時，才可以安裝共用外掛程式。 在非桌上出版本的 Internet Explorer 10 和11中，無法使用這些功能。 請注意，已不再支援 Firefox 和 Safari 版本12.0 和更新版本。
  
&#x2777; 在支援的 Windows 7 上，Windows Server 2008 R2 和 Macintosh 作業系統，所有功能均可供使用，包括電腦型語音、影片、應用程式查看、應用程式共用、桌面觀賞和桌面共用。 若要使用這些功能，您必須在出現提示時安裝外掛程式。 請注意，已不再支援 Mac OS X 版本10.7。  此外請注意，不會在 OS X 10.15 或更新版本上安裝 web 應用程式。  我們建議使用最新版本的 Mac 版商務用 Skype，它支援匿名加入案例。
  
&#x2778; 從 Windows 上的 Chrome 存取 web app，將會啟動小型程式，在內嵌的 Internet Explorer frame 中載入 web 應用程式。 此程式需要安裝其中一個支援的 Internet Explorer 版本，才能正確載入 Web 應用程式。
  
> [!NOTE]
> Microsoft 365 和 Office 365 使用者可以使用 Internet Explorer 10 或更新版本商務用 Skype。 
  
### <a name="skype-meetings-app"></a>Skype 會議 App

Skype 會議應用程式會在使用 Windows 10 的電腦上執行，Windows 8.1，Windows 8，Windows 7，且已安裝32和64位 Internet Explorer 11 或更新版本。 
  
對於任何其他相依性，請參閱[Skype 會議應用程式的支援平臺](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac 版商務用 Skype

Mac 版商務用 Skype 會在使用 macOS 版本10.8 或更新版本的電腦上執行。 

## <a name="hardware-requirements"></a>硬體需求
<a name="OS-Browser"> </a>

電腦硬體需求是由作業系統和瀏覽器所決定。 語音和電話語音功能需要麥克風和揚聲器、帶麥克風的耳機，或與電腦相容的同等裝置。 影片功能需要與電腦相容的影片裝置。 如需有關影片硬體支援和預期的影片品質的詳細資訊，請參閱[商務用 Skype 用戶端影片解析度](video-resolutions.md)。
  
## <a name="network-requirements"></a>網路要求
<a name="Network"> </a>

如果商務用 Skype Web 應用程式或 Skype 會議應用程式的使用者遇到會議連線問題，則組織的網路基礎結構可能並未設定為支援[Office 365 URLs 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述的 Office 365。 不論是由商務用 Skype 線上還是商務用 Skype Server 的使用者建立會議，都是如此。 
  
如果使用者位於未設定為所述的網路上，許多應用程式功能可能也可能不會運作，而且可能無法連線到會議。
  
## <a name="supported-meetings-features"></a>支援的會議功能
<a name="BKMK_Conferencing"> </a>

下表比較商務用 Skype 用戶端、商務用 Skype Web 應用程式、Skype 會議應用程式和 Lync Web App 的使用者可用的會議功能。 已列出 lync Web App 以進行功能比較目的：如果在 Lync 2013 server 上主控會議，則使用者只會下載和使用 Lync Web App。

| 功能/功能 | 商務用 Skype 2016 或2019用戶端 | Mac 用戶端上的商務用 Skype | Skype 會議 App | 商務用 Skype Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|新增電腦音訊  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |
|新增影片  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |
|針對已驗證的參與者將音訊切換到電話  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|將音訊切換為來賓參與者的電話  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|查看多方影片 (圖庫 view)   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|視訊為基礎的畫面共享  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (僅供查看)   <br/> |||
|使用會議中的簡報者控制項  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|存取詳細的會議名單  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|參與多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|將 IM 郵件設為高重要性  <br/> |&#x2714;|||||
|在啟用) 時共用桌面 (  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |&#x2714; (需要外掛程式)   <br/> |
|在啟用的情況中共用程式 ()   <br/> |&#x2714;||僅 Windows 上 (&#x2714;; 需要外掛程式)   <br/> |僅 Windows 上 (&#x2714;; 需要外掛程式)   <br/> |僅 Windows 上 (&#x2714;; 需要外掛程式)   <br/> |
|取得另一個使用者的共用桌面或程式控制權  <br/> |&#x2714;||僅 Windows 上 (&#x2776; &#x2714;; 需要外掛程式)   <br/> |僅 Windows 上 (&#x2776; &#x2714;; 需要外掛程式)   <br/> |僅 Windows 上 (&#x2776; &#x2714;; 需要外掛程式)   <br/> |
|讓其他使用者取得您共用的桌面或程式的控制權  <br/> |&#x2714;|||||
|在啟用) 時新增匿名參與者 (  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|依名稱邀請參與者  <br/> |&#x2714;|&#x2714;||||
|依電話號碼邀請參與者  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|透過電子郵件邀請參與者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|使用電話撥入式音訊會議  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|啟動 [立即開會] 會議  <br/> |&#x2714;|&#x2714;||||
|錄製會議  <br/> |&#x2714;|||||
|新增及下載附件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|新增及呈現 Microsoft PowerPoint 檔案  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|流覽 Microsoft PowerPoint 檔案  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|新增及編輯 OneNote 會議筆記  <br/> |&#x2714;||僅限編輯 (不新增)   <br/> |僅限編輯 (不新增)   <br/> |僅限編輯 (不新增)   <br/> |
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|進行投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|與其他人共用的 Upload 檔案  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|排程會議或會議  <br/> |Outlook 或商務用 Skype Scheduler  <br/> |Outlook 或商務用 Skype Scheduler  <br/> |商務用 Skype Scheduler  <br/> |商務用 Skype Scheduler  <br/> |商務用 Skype Scheduler  <br/> |
|Q &amp; A 主管  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|停用出席者影片  <br/> |&#x2714;|||||
|停用會議 IM  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|靜音物件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|讓每個人成為出席者  <br/> |&#x2714;|||||
|產生 Skype 會議廣播  <br/> |&#x2714;|||||
   
 &#x2776; 參與者無法控制 Mac 版商務用 Skype、Lync for mac 2011 或 Communicator for mac 2011 使用者共用的桌面。 這也不適用於最大 OSX 商務用 Skype Web 應用程式。
  
 &#x2777; 針對商務用 Skype 線上，此功能需要 Microsoft PSTN 會議、Exchange 整合通訊或協力廠商音訊會議提供者。
  
 &#x2778; Lync for Mac 2011 用戶端當商務用 Skype Web 應用程式在會議中共用時，無法查看 Microsoft Office 2013 PowerPoint 簡報。
  
## <a name="known-issues-and-troubleshooting"></a>已知問題及疑難排解
<a name="BKMK_Conferencing"> </a>

針對使用者，這些應用程式的 [線上](https://aka.ms/smahelp) 說明隨時可供使用。 IT 專業人員應該注意下列問題：
  
- 如果使用者位於未設定為符合 [網路需求](meetings-clients.md#Network)的網路上，許多應用程式功能可能或不會運作，而且可能無法連線到會議。
    
- 有些使用者可能具有公司管理的電腦，且已禁用安裝應用程式的許可權。 對於這些使用者，這兩個應用程式都不是一個選項，但是 [smart phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) 和 [平板](https://products.office.com/skype-for-business/download-app?tab=tabs-2) 電腦使用者可能會安裝可用於參加會議的廉價行動用戶端。
    
    其他安裝問題也會包含在 [說明] [主題](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)中。 
    
- 使用者第一次執行會議應用程式時，可能會看到防火牆警告。 他們可能會收到開啟埠，以優化體驗，而且可能需要在其可能不具備的電腦上使用系統管理員許可權。 應用程式仍會運作，使用者可以安全地拒絕開啟所要求的埠。 
    
- 您必須在 Internet Explorer 中[啟用 ActiveX 但不進行篩選](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)，即使 IE 並非您的預設瀏覽器也是一樣。 在商務用 Skype Web 應用程式中，ActiveX 控制項（即新增其他功能至 Web 應用程式或其他程式的小模組）是音訊、影片和螢幕共用的必要條件。
    
- 為了讓商務用 Skype Web 應用程式的某些功能正常運作，您必須允許瀏覽器在電腦或裝置上[儲存 cookie](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) 。
    
- 您可能需要在您的瀏覽器中[開啟 JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支援，有些商務用 Skype Web 應用程式功能才能如預期的方式運作。
    
### <a name="aes-support"></a>AES 支援 

從商務用 Skype Server 2015 CU5 起，ASP.NET 4.6 不支援 AES，這可能會導致 Skype 會議應用程式無法啟動。 [因 ASP .net 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 所產生的密碼編譯需求更詳細。
  
## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[在商務用 Skype Server 中部署 Web 可下載的用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 會議應用程式的支援平臺](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
