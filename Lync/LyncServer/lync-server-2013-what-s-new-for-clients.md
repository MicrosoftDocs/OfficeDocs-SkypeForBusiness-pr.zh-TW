---
title: Lync Server 2013：用戶端最新訊息
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
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a>Lync Server 2013 中的用戶端最新訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

Microsoft Lync 2013 具有重新設計的使用者介面和重要的新功能。 就管理員而言，用戶端現已隨附于 Office 安裝程式，提供更簡單的方法來部署 Office 及自訂貴組織中的用戶端。

<div>


> [!NOTE]  
> 如需 Lync 2013 使用者介面更新的圖例視圖，請參閱「Lync 2013 的新增功能」 <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>。



</div>

<div>

## <a name="integration-with-office-setup"></a>與 Office 安裝程式整合

Lync 2013 的 Lync 2013 用戶端和線上會議增益集（可支援 Outlook 訊息和共同作業用戶端內的會議管理）現在都包含在 Office 2013 設定程式中。

在舊版 Lync 和 Office Communicator 中，您可以使用 Windows 安裝程式屬性來自訂及控制 Office 安裝。 由於 Lync 2013 是與 Office 設定整合，因此您可以使用下列方法來自訂 Lync 2013 設定：

  - 使用 Office 自訂工具 (OCT)

  - 使用 Config.xml 執行安裝任務

  - 使用設定命令列選項

<div>


> [!NOTE]  
> Lync 2013 安裝程式不會卸載舊版的 Lync 或 Office Communicator。 Lync 2013 用戶端與其他 Lync 或 Office Communicator 用戶端並排安裝



</div>

如需詳細資訊，請參閱[在 Lync Server 2013 中部署 lync 用戶端](lync-server-2013-deploying-lync-clients.md)。

</div>

<div>

## <a name="group-policy-deployment"></a>群組原則部署

由於 Lync 2013 現已包含在 Office 設定中，因此部署 Lync 群組原則設定的方法已變更。 在舊版的 Lync 和 Office Communicator 中，您可以使用 Communicator 來定義群組原則設定，但在 Lync 2013 中，您現在可以使用 Lync ADMX 及 ADML 與 Office 群組原則一起提供的管理範本管理範本。

如需詳細資訊，請參閱[Lync 2013 的群組原則設定](lync-server-2013-group-policy-settings-for-lync-2013.md)。

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a>Outlook 排程增益集更新

Lync 2013 的線上會議增益集包含會議邀請自訂及新的會議選項。

  - 系統管理員可以新增自訂標誌、支援 URL、合法免責聲明 URL 或自訂的頁尾文字，來自訂群組織的會議邀請。 如需詳細資訊，請參閱[在 Lync Server 2013 中自訂線上會議增益集](lync-server-2013-customizing-the-online-meeting-add-in.md)。

  - 新的出席者靜音控制項可讓會議召集人依預設將出席者音訊和影片設為靜音的會議進行排程。

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a>虛擬桌面基礎結構外掛程式

Lync 2013 用戶端現在支援虛擬桌面基礎結構（VDI）環境中的音訊和視頻。 使用者可以將音訊或視頻裝置（例如耳機或相機）連線至本機電腦（例如瘦用戶端或用途電腦）。 使用者可以連線到虛擬機器、登入在虛擬機器上執行的 Lync 2013 用戶端，並參與即時音訊與視頻通訊，如同用戶端在本機執行。 虛擬桌面環境支援下列功能：

  - 音訊與影片的裝置整合，包括下列各項：
    
      - 從裝置呼叫控制
    
      - 裝置上的目前狀態整合
    
      - 多個 HID （人體學介面裝置）支援

  - 位置與緊急服務支援。

  - 支援所有 Lync 形式，包括 IM、音訊、影片、應用程式共用、桌面共用、PowerPoint 共用、白板和檔案傳輸。

  - 在人對通話和電話會議中進行音訊與視頻支援。

如需有關部署 VDI 外掛程式的資訊，請參閱[在 Lync Server 2013 中部署 LYNC VDI 外掛程式](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。

</div>

<div>

## <a name="video-enhancements"></a>影片增強功能

有幾項新功能可大大增強會議參與者的影片體驗。

  - 影片是透過臉部偵測和智慧型組幀來加強，因此參與者的影片會移動，以協助將其放在框架中。

  - 在雙方通話和多方會議中現在支援高解析度的影片。 使用者可以體驗高達 HD 1080P 的解析度。

  - 參與者可以從不同的會議版面配置中選取： [庫視圖] 會顯示所有參與者的圖片或影片;[演講者] 視圖會顯示會議內容，且只顯示目前演講者的影片或圖片;[簡報] 視圖只會顯示會議內容;精簡查看只顯示會議控制項。

  - 使用新的圖庫功能，參與者可以同時查看多個視頻摘要。 如果會議的參與者超過五個，則只有最活躍參與者的影片摘要會出現在頂端列中，而其他參與者則會顯示圖片。

  - 參與者可以使用 [視頻釘選]，選取一或多個可用的影片摘要，讓它們隨時可見。

  - 簡報者可以使用 [影片焦點] 功能來選取一個人員的影片摘要，讓會議中的每位參與者都只會看到該參與者。

</div>

<div>

## <a name="chat-room-integration"></a>聊天室整合

Lync 2013 現在已整合 Lync 2010 群組聊天先前提供的功能。 不再需要個別的群組聊天用戶端。

  - 在 Lync 2013 中，使用者可以搜尋聊天室、新增聊天室給他們的連絡人、監控聊天室活動，以及讀取及張貼訊息。

  - 使用者可以建立主題摘要，以便在其中一個聊天室中的某人新增包含特定關鍵字的文章時收到通知。

  - 使用者可以使用新的 [**持續聊天**] 選項頁面，設定當人員將訊息張貼到聊天室時，要套用的通知通知與音效。

</div>

<div>

## <a name="lync-web-app-updates"></a>Lync Web App 更新

Lync Web App 是 Lync Server 2013 會議的網路式會議用戶端。 在這個版本中，將電腦音訊和影片新增至 Lync Web App，可為沒有在本機安裝 Lync 用戶端的任何人提供完整的會議體驗。 會議參與者可存取所有共同作業及共用功能及簡報者會議控制項。

當使用者嘗試加入會議，但沒有本機安裝的用戶端時，會開啟 Lync Web App。 如果您想要允許其他選項加入會議，您可以設定會議加入頁面;請參閱在部署檔中的[Lync Server 2013 中的 [設定會議加入] 頁面](lync-server-2013-configuring-the-meeting-join-page.md)。

由於 Lync Web App 的增強功能，因此無法使用 Lync Server 2013 的更新版本的出席者。 Lync Web App 是您組織外部參與者所選擇的用戶端。 您不需要安裝本機用戶端，不過音訊、影片和共用功能需要在第一次使用時才安裝外掛程式。

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a>適用于行動用戶端更新的 Lync 2013

除了增強的目前狀態、連絡人及 IM 功能之外，Lync 2013 行動用戶端現在提供透過網際網路和行動資料連線進行語音及視頻通話。 在行事曆中的 [行事曆] 專案中，行動使用者可以加入 Lync 語音及視訊會議。 如需 Lync 2013 行動用戶端的詳細資訊，請參閱[在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a>Lync 2013 使用者介面更新

<div>

## <a name="accessibility-updates"></a>協助工具更新

Lync 2013 包含幾個新的協助工具功能。

  - Lync 2013 支援高 DPI 解析度，讓使用者能夠針對125% 和150% 點每英寸調整文字與圖形。

  - Lync 提供高對比支援，讓使用者介面在 Windows 中與高對比主題搭配使用時，能保持完全正常運作。

  - Lync 提供的鍵盤快速鍵超過100個，因此使用者無需滑鼠就能存取重要的功能。 例如，使用者可以按 Alt + C 來接受來電，或按 Alt + I 來忽略它，而不需要使用 tab 鍵或設定焦點。 按下（Alt + Q）會結束通話，（Ctrl + N）會啟動 OneNote，而（Alt + T）會開啟 [工具] 功能表。

  - Lync 2013 中的大量螢幕閱讀程式支援可確保在啟用螢幕閱讀器時，大聲讀出所有通知、傳入要求和立即訊息。

</div>

<div>

## <a name="presence-while-sharing"></a>共用時的目前狀態

當 Lync 偵測到某個使用者正在共用時，Lync 會自動為該使用者指派簡報狀態。 除非給寄件者指派了工作組隱私權關係，否則此狀態會封鎖所有傳入通訊。 如果使用者完全在輔助監視器上使用共用功能，Lync 不會指派簡報目前狀態。

</div>

<div>

## <a name="conversation-window-updates"></a>交談視窗更新

重新設計的交談視窗可讓您更快速地存取重要功能。

  - 透過新的 [索引標籤式交談] 功能，使用者現在可以在單一交談視窗中保留所有的 Im 和聊天室。 [交談] 視窗左側的索引標籤可讓使用者輕鬆地在所有活動交談中進行流覽。

  - 使用者可以將個別的交談醒目提示到另一個視窗，然後調整視窗大小。 他們也可以將視窗放回到主要交談視窗中。

  - 當使用者登出並重新登入 Lync 時，Lync 2013 會重新開啟使用者的交談。

  - 使用者可以將 IM、影片、程式共用、桌面共用或 web 會議工具（白板、會議記事、共用筆記本及附件）快速新增至任何交談。

  - 在共用影片或內容的會議中，使用者可以彈出會議影片或共用內容，然後調整視窗大小。

</div>

<div>

## <a name="lync-main-window-updates"></a>Lync 主視窗更新

新的精簡外觀會保留熟悉的功能，例如**今天所發生的問題？** 記事欄位、狀態選取器，以及**設定您的位置**選擇器。

  - 啟用聊天室之後，使用者會在主要 Lync 頁面上看到新的**聊天室**圖示。 使用聊天室**圖示，** 使用者可以快速存取其聊天室和篩選。

  - 使用者可以按一下 [視圖] 圖示，切換到 [**連絡人**] 視圖、[**聊天室**] 視圖、[**交談**] 視圖或 [**電話**] 視圖。

  - 如果使用者已遷移至 Exchange 2013，就可以上傳高解析度的圖片。

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a>連絡人視圖和連絡人卡片更新

Lync 2013 提供使用者在**連絡人**視圖中查看連絡人與群組的不同方式。

  - 在新的整合連絡人存放區中，使用者的 Lync 連絡人被遷移至 Exchange 2013 之後，使用者就可以從 Lync 2013、Outlook 或 Outlook Web App 存取及管理他們的連絡人，而且他們的最愛仍保持同步處理。 例如，如果使用者在 Outlook 中新增連絡人至 [我的最愛]，該連絡人會出現在 Lync 2013 的 [我的最愛] 群組中。

  - 如果您已新增並設定 XMPP proxy 和 XMPP gateway，使用者可以新增來自 XMPP 合作夥伴的連絡人以進行立即訊息和目前狀態。

  - 新的新增**連絡人不在「我的組織」中**」功能可讓使用者輕鬆地新增組織外部的人員。

  - 新的 [我的最愛 **]** 群組可讓使用者建立使用者最常聯絡的人員清單，以快速存取。

  - 使用者可以使用新的 [**連絡人清單**選項] 頁面，選擇使用者要排序及顯示連絡人的方式。 使用者可以選取一個展開的雙行視圖來顯示連絡人的圖片，或是一個簡潔的單行視圖。 使用者也可以依字母順序或依可用性排序連絡人。

</div>

<div>

## <a name="conferencing-updates"></a>會議更新

Lync 2013 提供數個功能，可增強會議功能。

  - 根據會議類型而定，使用者現在可以將物件設為靜音，並允許或封鎖在排程會議時的影片共用。 您可以在 [**會議選項**] 頁面上使用這些選項，建議您在超過20名參與者的大型會議中使用這些選項。

  - 您可以在會議室輕鬆使用音訊控制項，讓使用者能夠控制音訊選項，例如靜音、取消靜音、變更裝置等。

  - 當您共用程式時，如果需要使用多個程式，使用者可以選取多個要共用的程式。

  - 使用者現在可以上傳 PowerPoint 檔案，並將滑鼠指標放在投影片上，以顯示影片控制項（例如播放、暫停和音訊控制項），來上傳包含影片剪輯的簡報。

  - 在會議中，使用者可以使用 [**其他選項**（**...**）] 功能表中的 [**合併此通話**]，將其他開啟的交談合併至會議中。

  - 若要查看參與者的名稱，使用者可以將滑鼠游標暫留在 [**查看參與者**] 按鈕上，或按一下 [**顯示參與者清單**] 以將面板固定在會議中。

  - 根據會議類型，使用者可以從數個不同的內容和參與者視圖中進行選取。

  - 會議錄製會自動儲存為在 Windows Media Player （會議格式）中播放的格式。 使用者可以輕鬆地與任何人共用檔案，或使用錄製管理員中的 [**發佈**] 功能，將錄製張貼到共用位置。

  - OneNote 可讓您在會議中共同作業。 在會議期間，使用者可以在會議之後使用 OneNote 來記錄筆記，或使用共用筆記本並即時與會議參與者共同編輯會議。 所有小組成員都可以存取共用筆記，以參與資訊、集體討論想法，或使用筆記本頁面做為虛擬白板。 在會議中共用的人員和內容會自動新增到筆記中。

  - 使用者可以使用會議會議室底部的 [**共用內容] 和 [引導會議活動]，** 在內容類型之間切換。 使用者也可以使用 [**管理簡報內容**] 功能表來選擇要共用的內容。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[規劃 Lync Server 2013 中的用戶端](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

