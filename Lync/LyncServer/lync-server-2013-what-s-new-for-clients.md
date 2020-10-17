---
title: Lync Server 2013：用戶端的新功能
description: Lync Server 2013：用戶端的新功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90c1b93666b556c7ce7c4f3d94bea583dbf9b1a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546129"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a>Lync Server 2013 中用戶端的新功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

Microsoft Lync 2013 具有重新設計的使用者介面及重要的新功能。 針對系統管理員，用戶端現在已包含在 Office 安裝程式中，可提供更簡潔的方法來部署 Office 及自訂群組織中的用戶端。

<div>


> [!NOTE]  
> 如需 Lync 2013 使用者介面更新的圖解視圖，請參閱的「Lync 2013 的新功能」 <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> 。



</div>

<div>

## <a name="integration-with-office-setup"></a>與 Office 安裝程式整合

Lync 2013 （支援來自 Outlook 郵件和共同作業用戶端的會議管理）的 Lync 2013 用戶端和線上會議增益集現在已包含在 Office 2013 安裝程式中。

在舊版的 Lync 和 Office Communicator 中，您可以使用 Windows Installer 內容自訂和控制 Office 安裝。 因為 Lync 2013 已與 Office 安裝程式整合，您可以使用下列方法來自訂 Lync 2013 安裝程式：

  - 使用 Office 自訂工具 (OCT)

  - 使用 Config.xml 執行安裝工作

  - 使用安裝程式命令列選項

<div>


> [!NOTE]  
> Lync 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。 Lync 2013 用戶端會與其他 Lync 或 Office Communicator 用戶端同時安裝



</div>

如需詳細資訊，請參閱 [在 Lync Server 2013 中部署 Lync 用戶端](lync-server-2013-deploying-lync-clients.md)。

</div>

<div>

## <a name="group-policy-deployment"></a>群組原則部署

因為 Lync 2013 現在已包含在 Office 安裝程式中，所以部署 Lync 群組原則設定的方法已變更。 在舊版的 Lync 和 Office Communicator 中，您可以使用 Communicator 來定義群組原則設定，而在 Lync 2013 中，您現在可以使用 Lync ADMX 和 ADML 系統管理範本，以及 Office 群組原則系統管理範本提供。

如需詳細資訊，請參閱 [Lync 2013 的群組原則設定](lync-server-2013-group-policy-settings-for-lync-2013.md)。

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Outlook 排程增益集更新

Lync 2013 的線上會議增益集包括會議邀請自訂及新的會議選項。

  - 管理員可以藉由新增自訂標誌、支援 URL、法律免責聲明 URL 或自訂頁尾文字，自訂組織的會議邀請。 如需詳細資訊，請參閱 [在 Lync Server 2013 中自訂線上會議增益集](lync-server-2013-customizing-the-online-meeting-add-in.md)。

  - 新的出席者靜音控制讓會議召集人可在排程會議時，將出席者音訊及視訊預設為靜音。

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>虛擬桌面基礎結構外掛程式

Lync 2013 用戶端現在支援虛擬桌面基礎結構 (VDI) 環境中的音訊和影片。 使用者可以將音訊和視訊裝置 (例如，耳機或相機) 連線至本機電腦 (例如，精簡型用戶端或重新設定功能的電腦)。 使用者可以連線至虛擬機器，登入虛擬機器上執行的 Lync 2013 用戶端，並參與即時音訊和視頻通訊，如同用戶端在本機執行。 在虛擬桌面環境中支援下列功能：

  - 音訊及視訊的裝置整合，包括下列項目：
    
      - 裝置的通話控制
    
      - 裝置上的狀態整合
    
      - 多重 HID (人性化介面裝置) 支援

  - 位置及緊急服務支援。

  - 支援所有 Lync 形式，包括 IM、音訊、影片、應用程式共用、桌面共用、PowerPoint 共用、白板及檔案傳輸。

  - 人對人通話及會議通話中的音訊及視訊支援。

如需部署 VDI 外掛程式的相關資訊，請參閱 [在 Lync Server 2013 中部署 LYNC VDI 外掛程式](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。

</div>

<div>

## <a name="video-enhancements"></a>視訊增強功能

許多新的功能大幅增強會議參與者的視訊體驗。

  - 視訊中加入了臉部偵測及智慧框架增強功能，讓參與者的視訊會移動，將參與者保持在框架中心。

  - 雙方通話及多方會議現在支援高畫質視訊。使用者可以體驗到高達 HD 1080P 的解析度。

  - 參與者可以選取不同的會議配置：「圖庫檢視」會顯示所有參與者的圖片或視訊；「演講者檢視」會顯示會議內容以及僅目前演講者的視訊或圖片；「簡報檢視」僅會顯示會議內容；「精簡檢視」僅會顯示會議控制。

  - 透過新的圖庫功能，參與者可以同時見到多重視訊播放。如果會議有超過五位參與者，頂端列中會出現最積極參與者的視訊播放，對於其他參與者則顯示圖片。

  - 參與者可以使用視訊固定功能，選取讓一或多個可用的視訊播放隨時可見。

  - 簡報者可以使用「視訊焦點」功能，選取某個人的視訊播放，讓會議中所有參與者僅看到該參與者。

</div>

<div>

## <a name="chat-room-integration"></a>聊天室整合

Lync 2013 現在會整合 Lync 2010 群組聊天先前提供的功能。 不再需要個別的群組聊天用戶端。

  - 在 Lync 2013 中，使用者可以搜尋聊天室、將聊天室新增至其連絡人、監控聊天室活動，以及閱讀和張貼訊息。

  - 使用者可以建立主題摘要，如果某人在他們其中一個聊天室中新增包含特定關鍵字的文章時，使用者就會收到通知。

  - 透過新的 **[常設聊天室]** 選項頁面，使用者可以設定當有人在他們的聊天室張貼訊息時要套用的通知警示與音效。

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App 更新

Lync Web App 是 Lync Server 2013 會議的 Web 式會議用戶端。 在此版本中，對 Lync Web App 的電腦音訊和影片的加入，可為沒有在本機安裝 Lync 用戶端的任何人提供完整的會議體驗。 會議參與者可存取所有共同作業與共用功能，以及簡報者會議控制。

當使用者嘗試加入會議，但沒有本機安裝的用戶端時，Lync Web App 隨即開啟。 如果您想要允許其他選項加入會議，您可以設定會議加入頁面;請參閱部署檔中的 [Lync Server 2013 中的設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md) 。

由於 Lync Web App 的增強功能，Lync Server 2013 不提供更新版本的出席者。 Lync Web App 是您組織外部參與者的選擇用戶端。 不需要安裝本機用戶端，但在第一次使用音訊、視訊及共用功能時，需要安裝外掛程式。

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>Lync 2013 用於行動用戶端更新

除了增強的目前狀態、連絡人及 IM 功能之外，Lync 2013 行動用戶端現在也會透過網際網路和行動電話資料連線提供語音和影片呼叫。 使用 [行事曆] 專案中的會議連結的單一點擊，行動使用者便可加入 Lync 語音和影片會議。 如需 Lync 2013 行動用戶端的詳細資訊，請參閱 [在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013 使用者介面更新

<div>

## <a name="accessibility-updates"></a>協助工具更新

Lync 2013 包含數個新的協助工具。

  - Lync 2013 支援高 DPI 解析度，讓使用者能夠調整125% 的文字和圖形，以及每英寸150% 點。

  - Lync 提供高對比支援，讓使用者介面在與 Windows 中的高對比主題搭配使用時仍然保持完整運作。

  - Lync 提供超過100個鍵盤快速鍵，讓使用者不必使用滑鼠即可存取重要的功能。 例如，使用者可以按 Alt+C 接受通話，或 Alt + I 忽略通話，而不需要索引標籤或設定焦點。 按 (Alt+Q) 結束通話、(Ctrl+N) 啟動 OneNote，以及 (Alt+T) 開啟 [工具] 功能表。

  - Lync 2013 中的廣泛螢幕讀取器支援，可確保在啟用螢幕閱讀器時，高聲閱讀所有通知、傳入要求和立即訊息。

</div>

<div>

## <a name="presence-while-sharing"></a>共用時的狀態

當 Lync 偵測到使用者正在共用時，Lync 會自動為使用者指派展示目前狀態。 此狀態會封鎖所有的傳入通訊，除非已指派工作群組私人關係給傳送者。 如果使用者完全在第二個監視器上使用共用功能，Lync 便不會指派呈現狀態。

</div>

<div>

## <a name="conversation-window-updates"></a>交談視窗更新

重新設計的交談視窗對重要功能提供了更快的存取方式。

  - 透過新的分頁交談功能，使用者現在可以將所有 IM 及聊天室保持在一個交談視窗中。交談視窗左側的分頁可讓使用者在所有使用中交談中輕鬆瀏覽。

  - 使用者可以將個別交談取消固定到個別視窗中，然後調整視窗大小。也可將視窗固定回主要的交談視窗中。

  - 當使用者登出並重新登入 Lync 時，Lync 2013 會重新打開使用者的交談。

  - 使用者可以在任何交談中快速新增 IM、視訊、程式共用、桌面共用或 Web 會議工具 (白板、會議記錄、共用筆記本及附件)。

  - 在共用視訊或內容的會議中，使用者可以取消固定會議視訊或共用內容，然後調整視窗大小。

</div>

<div>

## <a name="lync-main-window-updates"></a>Lync 主視窗更新

嶄新的簡化外觀保留了熟悉的功能，例如 **[今天有什麼新鮮事？]** 記錄欄位、狀態選取器以及 **[設定您的位置]** 選取器。

  - 啟用聊天室時，使用者會在主要 Lync 頁面上 **看到新的聊天室圖示** 。 透過 **[聊天室]** 圖示，使用者可以快速存取聊天室及篩選條件。

  - 使用者可以按一下檢視圖示切換至 **[連絡人]** 檢視、**[聊天室]** 檢視、**[交談]** 檢視或 **[電話]** 檢視。

  - 如果使用者已遷移至 Exchange 2013，可上傳高解析度圖片。

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>連絡人檢視及連絡人卡片更新

Lync 2013 為使用者提供不同的方式來查看其 **連絡人** 視圖中的連絡人和群組。

  - 在新的整合連絡人存放區中，使用者的 Lync 連絡人會遷移至 Exchange 2013 之後，使用者就可以從 Lync 2013、Outlook 或 Outlook Web App 存取及管理其連絡人，其最愛保持同步。 例如，如果使用者將連絡人新增至 Outlook 中的 [我的最愛]，該連絡人會出現在 Lync 2013 的 [我的最愛] 群組中。

  - 如果已新增並設定 XMPP Proxy 及 XMPP 閘道，使用者就可以新增以 XMPP 為基礎之協力廠商的連絡人，用於立即訊息與目前狀態。

  - 新的 **[新增非組織內部的連絡人]** 功能讓使用者可輕鬆新增組織外人員。

  - 新的 **[我的最愛]** 群組讓使用者可以建立使用者最常連絡的人員清單，以供快速存取。

  - 使用者可以使用新的 **[連絡人清單]** 選項頁面，選擇使用者如何排序及顯示連絡人的方式。使用者可以選擇展開的雙行檢視 (顯示連絡人圖片) 或緊縮的單行檢視。使用者也可以依字母順序或依顯示狀態來排序連絡人。

</div>

<div>

## <a name="conferencing-updates"></a>會議更新

Lync 2013 提供許多對會議功能的增強功能。

  - 視會議類型而定，使用者現在可以在排程會議時將觀眾設為靜音，以及允許或封鎖視訊共用。這些選項提供於 **[會議選項]** 頁面，建議使用於超過 20 位參與者的大型會議。

  - 會議室中容易使用的音訊控制讓使用者可以控制音訊選項，例如靜音、取消靜音、變更裝置等。

  - 共用程式時，如果使用者需要使用一個以上的程式，則可以選取共用多個程式。

  - 使用者現在可以上傳包含視訊剪輯的簡報：上傳 PowerPoint 檔案，然後將滑鼠指向投影片以顯示視訊控制，例如播放、暫停及音訊控制。

  - 在會議進行中，使用者可以使用 **[更多選項]** (**[...]**) 功能表上的 **[將這個通話合併為]**，將其他開啟交談合併至會議中。

  - 如要檢視參與者的名稱，使用者可以將滑鼠暫留在 **[檢視參與者]** 按鈕上，或按一下 **[顯示參與者清單]**，將面板固定在會議中。

  - 視會議類型而定，使用者可以選取許多不同的內容及參與者檢視。

  - 會議錄製會自動儲存為可在 Windows Media Player 中播放的格式 (MP4)。使用者可以輕鬆與任何人共用檔案，或使用錄製管理員中的 **[發佈]** 功能，將錄製張貼到共用的位置。

  - OneNote 讓會議中共同作業有了新方法。在會議進行中，使用者可以使用 OneNote 作筆記，供會議後私人之用，或者使用共用筆記本，與會議參與者進行即時共同編輯。所有的小組成員都可以存取共用的記事來提供資訊、腦力激盪，或使用筆記本頁面作為虛擬白板。在會議中共用的人員及內容會自動新增到 Notes。

  - 使用者可以使用會議室底端的 **[共用內容並引導會議活動]**，在內容類型之間切換。使用者還可以使用 **[管理簡報內容]** 功能表，選擇要共用的內容。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃用戶端](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

