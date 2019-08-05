---
title: 規劃會議用戶端 (Web App 與會議應用程式)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: '摘要: IT 專業人員應該在規劃商務用 Skype Server 時, 查看商務用 Skype Web App 與 Skype 會議應用程式的支援需求。 本文不適用於這些 app 的使用者。'
ms.openlocfilehash: a2bc418b9179a63452c5d4fdd1990676f9db4b14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187876"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>規劃會議用戶端 (Web App 與會議應用程式)
 
**摘要:** IT 專業人員應該在規劃商務用 Skype Server 時, 查看商務用 Skype Web App 與 Skype 會議應用程式的支援需求。 本文不適用於這些 app 的使用者。
  
一旦您已實施商務用 Skype Server, 貴組織的使用者可能會將商務用 Skype 用戶端安裝為部署程式的一部分。 
  
稍後, 這些使用者可能會建立會議並邀請來自組織外部的使用者, 而這些會議受邀者可能不會擁有任何版本的商務用 Skype 用戶端。 當使用者按一下會議邀請的 URL 時, 系統就會不會偵測到用戶端, 且不需要商務用 Skype 用戶端的被邀請者, 就會要求您下載並安裝輕量、會議的用戶端, 讓他們可以加入會議。
  
> [!NOTE]
> 商務用 Skype Web App 和 Skype 會議應用程式僅適用于嘗試登入會議而不需要商務用 Skype。 這些應用程式的使用者說明是[https://aka.ms/smahelp](https://aka.ms/smahelp)在。 
  
> [!NOTE]
> 您無法預先安裝商務用 Skype Web App 或 Skype 會議應用程式, 但[智慧手機](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)電腦使用者可能能夠安裝可供您參與會議的廉價行動用戶端。
  
根據預設, 託管會議的伺服器會引導使用者下載並安裝商務用 Skype Web App 來加入會議。 商務用 Skype Web App 儲存在前端伺服器上, 並傳送給會議出席者。 
  
在商務用 Skype Server、Skype 會議應用程式 (Windows 版) 和商務用 Skype for Mac (Mac 版) 上, 都提供從 CU5 開始的商務用 skype Web App 取代, 但提供替換應用程式需要額外的配置在[[啟用 Skype 會議] app 中所述, 以取代商務用 Skype Web app (選用)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。  如果啟用 Skype 會議應用程式和 Mac 版商務用 Skype, 使用者將會從 Office 365 內容傳遞網路 (CDN) 下載最新版本的 app, 而不是從商務用 Skype 伺服器下載。 針對商務用 Skype Server 2019, 使用 Skype 會議應用程式和 Mac 版商務用 Skype 是唯一的選項。
  
Skype 會議應用程式提供簡化的瀏覽器體驗, 可供您下載並安裝應用程式並加入會議, 包括針對 Internet Explorer 使用者的按一下 [加入]。 Skype 會議應用程式在可靠性與會議體驗上的商務用 Skype Web App 也有許多改良的功能。 
  
> [!NOTE]
> 從商務用 Skype Server 2015 CU5 或更新版本, 使用商務用 Skype Online 所保留的會議將不再傳送 clientless 使用者的商務用 skype Web App, 而是傳送 Skype 會議應用程式 (在 Windows 上) 或 Mac 版商務用 Skype (Mac 版)。 從商務用 Skype Server 2015 CU5 或更新版本, 如果您[啟用 Skype 會議 App 來取代商務用 Skype Web app (選用)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), clientless 使用者將會傳送 Skype 會議 App 或 Mac 版商務用 skype, 而不是商務用 Skype Web app。 
  
## <a name="software-requirements"></a>軟體需求
<a name="OS-Browser"> </a>

若要使用商務用 Skype Web App, 使用者必須具備下列其中一種受支援的作業系統和瀏覽器混合。 
  
**商務用 Skype Web App 的作業系統和最低瀏覽器支援**

| 作業系統 | 左邊 | 32與64位的 Internet Explorer 11 或更新版本 | 32與64位的 Internet Explorer 10 或更新版本 | 32與64位的 Internet Explorer 9 或更新版本 | 32與64位版本的 Safari 6.2.8-11. X | 32與64位版本的 Chrome 18. X 或更新版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是的  <br/> |是的  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |[是] &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/A  <br/> |是的  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |[是] &#x2778; <br/> |
|Windows 8 (以 Intel 為基礎) &#x2776; <br/> |N/A  <br/> |N/A  <br/> |是的  <br/> |N/A <br/> |N/A  <br/> |[是] &#x2778; <br/> |
|Windows 7 (含 SP1) &#x2777; <br/> |N/A  <br/> |是的  <br/> |不  <br/> |不  <br/> |N/A <br/>|[是] &#x2778; <br/> |
|Windows Server 2008 R2 (含 SP1) &#x2777; <br/> |N/A  <br/> |是的  <br/> |是的  <br/> |是的  <br/> |N/A <br/>|[是] &#x2778; <br/> |
|macOS 10.8 及更新版本 (以 Intel 為基礎) &#x2777; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |是的  <br/> |是的 <br/> |
   
&#x2776; 商務用 Skype Web App 瀏覽器外掛程式需要特定的共用外掛程式, 才能使用以電腦為基礎的語音、影片、共用及查看正在進行中的螢幕共用及其他功能。 當會議出席者加入會議或啟動其中一個功能時, 就會提供安裝共用外掛程式的選項。 在 Windows 8 和 Windows 8.1 上, 只有當您在桌上型電腦上執行 Internet Explorer 10 或 Internet Explorer 11 時, 才能安裝共用外掛程式。 這些功能不適用於非桌上出版本的 Internet Explorer 10 和11。 請注意, 已不再支援 Firefox 與 Safari 版本12.0 及更新版本。
  
&#x2777; 支援 Windows 7、Windows Server 2008 R2 和 Macintosh 作業系統, 所有功能都可以使用, 包括電腦式語音、影片、應用程式查看、應用程式共用、桌面查看和桌面共用。 若要使用這些功能, 您必須在出現提示時安裝外掛程式。 請注意, 已不再支援 Mac OS X 版本10.7。
  
從 Windows 上的 Chrome 存取 Web 應用程式 &#x2778; 會啟動小型程式, 以在內嵌的 Internet Explorer 框架中載入 Web 應用程式。 此程式需要安裝其中一個受支援的 Internet Explorer 版本, 才能正確載入 Web App。
  
> [!NOTE]
> Office 365 使用者可以在商務用 Skype 中使用 Internet Explorer 10 或更新版本。 
  
### <a name="skype-meetings-app"></a>Skype 會議應用程式

Skype 會議應用程式在使用 Windows 10、Windows 8.1、Windows 8、Windows 7 的電腦上, 在安裝32和64位 Internet Explorer 11 或更新版本的電腦上, 以應用程式的方式執行。 
  
針對任何其他相依性, 請參閱[Skype 會議應用程式支援的平臺](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac 版商務用 Skype

Mac 版商務用 Skype 會在使用 macOS 版本10.8 或更新版本的電腦上執行。 

## <a name="hardware-requirements"></a>硬體需求
<a name="OS-Browser"> </a>

電腦的硬體需求是由作業系統和瀏覽器決定。 語音和電話功能需要麥克風和喇叭、帶麥克風的耳機, 或與電腦相容的對等裝置。 影片功能需要與電腦相容的視頻裝置。 如需有關視頻硬體支援及預期的影片品質的詳細資訊, 請參閱[商務用 Skype 用戶端影片的解析度](video-resolutions.md)。
  
## <a name="network-requirements"></a>網路需求
<a name="Network"> </a>

如果商務用 Skype Web App 或 Skype 會議應用程式的使用者遇到會議連線問題, 可能是組織的網路基礎結構未設定為支援 Office 365, 如[Office 365 url 和 IP 位址範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述。 無論是由商務用 Skype Online 或商務用 Skype 伺服器的使用者建立會議, 都是這種情況。 
  
如果使用者位於未設定為 [已描述] 的網路上, 許多應用程式功能可能也可能無法運作, 而且他們可能無法連線到會議。
  
## <a name="supported-meetings-features"></a>支援的會議功能
<a name="BKMK_Conferencing"> </a>

此表格比較提供給商務用 Skype 用戶端、商務用 Skype Web App、Skype 會議應用程式及 Lync Web App 的使用者可用的會議功能。 Lync Web App 是針對功能比較目的而列出: 如果會議是在 Lync 2013 伺服器上託管, 則使用者只能下載並使用 Lync Web App。

| 功能/功能 | 商務用 Skype 2016 或2019用戶端 | Mac 版商務用 Skype 用戶端 | Skype 會議應用程式 | 商務用 Skype Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|新增電腦音訊  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |
|新增影片  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |
|針對經過驗證的參與者將音訊切換至手機  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|將音訊切換至來賓參與者的電話  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|查看多方影片 (圖庫視圖)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|以影片為基礎的畫面共用  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (僅限查看)  <br/> |||
|使用會議中的簡報者控制項  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|存取詳細的會議名單  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|參與多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|將 IM 訊息設為高重要性  <br/> |&#x2714;|||||
|共用桌面 (如果已啟用)  <br/> |&#x2714;|&#x2714;|&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |&#x2714; (需要外掛程式)  <br/> |
|共用程式 (如果已啟用)  <br/> |&#x2714;||&#x2714; (僅限 Windows 版; 需要外掛程式)  <br/> |&#x2714; (僅限 Windows 版; 需要外掛程式)  <br/> |&#x2714; (僅限 Windows 版; 需要外掛程式)  <br/> |
|控制其他使用者的共用桌面或程式  <br/> |&#x2714;||&#x2714; (僅限 Windows 上的 &#x2776;; 需要外掛程式)  <br/> |&#x2714; (僅限 Windows 上的 &#x2776;; 需要外掛程式)  <br/> |&#x2714; (僅限 Windows 上的 &#x2776;; 需要外掛程式)  <br/> |
|讓其他使用者控制您的共用桌面或程式  <br/> |&#x2714;|||||
|新增匿名參與者 (如果已啟用)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|依名稱邀請參與者  <br/> |&#x2714;|&#x2714;||||
|透過電話號碼邀請參與者  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|透過電子郵件邀請參與者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|使用電話撥入式音訊會議  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|啟動 [立即開會] 會議  <br/> |&#x2714;|&#x2714;||||
|錄製會議  <br/> |&#x2714;|||||
|新增及下載附件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|新增及展示 Microsoft PowerPoint 檔案  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|流覽 Microsoft PowerPoint 檔案  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|新增及編輯 OneNote 會議筆記  <br/> |&#x2714;||僅限編輯 (非新增)  <br/> |僅限編輯 (非新增)  <br/> |僅限編輯 (非新增)  <br/> |
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|進行投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|上傳檔案以與其他人共用  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|排程會議或會議  <br/> |Outlook 或商務用 Skype 網頁排程程式  <br/> |Outlook 或商務用 Skype 網頁排程程式  <br/> |商務用 Skype 網頁排程程式  <br/> |商務用 Skype 網頁排程程式  <br/> |商務用 Skype 網頁排程程式  <br/> |
|問&amp;: 管理員  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|停用出席者影片  <br/> |&#x2714;|||||
|停用會議 IM  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|將觀眾設為靜音  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|將所有人設為出席者  <br/> |&#x2714;|||||
|產生 Skype 會議廣播  <br/> |&#x2714;|||||
   
 &#x2776; 參與者無法控制由商務用 Skype for Mac、Lync for mac 2011 或 Mac 2011 使用者所共用的桌面。 這也不適用於最大 OSX 上的商務用 Skype Web App。
  
 針對商務用 Skype Online &#x2777;, 此功能需要 Microsoft PSTN 會議、Exchange 整合訊息或協力廠商音訊會議提供者。
  
 &#x2778; Lync for Mac 2011 用戶端在由商務用 Skype Web App 在會議中共用之後, 就無法透過 Microsoft Office 2013 PowerPoint 簡報進行流覽。
  
## <a name="known-issues-and-troubleshooting"></a>已知問題與疑難排解
<a name="BKMK_Conferencing"> </a>

針對使用者而言, 這些應用程式的[線上](https://aka.ms/smahelp)說明隨時可供使用。 IT 專業人員應該注意到下列問題:
  
- 如果使用者位於未設定符合[網路需求](meetings-clients.md#Network)的網路上, 許多應用程式功能可能也可能無法運作, 而且他們可能無法連線到會議。
    
- 有些使用者可能有公司管理的電腦, 且有已停用的許可權來安裝應用程式。 針對這些使用者, 這兩個應用程式都不是選項, 但[智慧手機](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)電腦使用者可能能夠安裝可供您參與會議的廉價行動用戶端。
    
    其他安裝問題也會包含在說明[主題](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)中。 
    
- 使用者第一次執行會議應用程式時, 可能會看到防火牆警告。 系統可能會提示您開啟埠以優化體驗, 而且可能需要在它們可能不具備的電腦上擁有系統管理員許可權。 App 應該仍能正常運作, 且使用者可以安全地拒絕開啟要求的埠。 
    
- 您必須在 Internet Explorer 中[啟用 ActiveX 但不進行篩選](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US), 即使 IE 不是您的預設瀏覽器也一樣。 在商務用 Skype Web App 中, ActiveX 控制項 (一個小型模組, 可新增其他功能至 Web App 或其他程式) 是音訊、影片和螢幕共用所必需的。
    
- 若要讓商務用 Skype Web App 的部分功能正常運作, 您必須允許您的瀏覽器[將 cookie 儲存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)在您的電腦或裝置上。
    
- 您可能需要在瀏覽器中[開啟 [JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支援], 才能讓某些商務用 Skype Web App 功能如期運作。
    
### <a name="aes-support"></a>AES 支援 

從商務用 Skype Server 2015 CU5, 不支援 ASP.NET 4.6 的 AES, 這可能會導致 Skype 會議應用程式無法啟動。 [ASP .net 4.5 的加密需求](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)有更多詳細資料。
  
## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[在商務用 Skype Server 中部署網頁下載用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 會議應用程式的支援平臺](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
