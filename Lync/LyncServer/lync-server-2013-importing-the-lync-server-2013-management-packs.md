---
title: Lync Server 2013：匯入 Lync Server 2013 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c753334ea9a046c6081a73ce70e4de00de9188
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>匯入 Lync Server 2013 管理套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

您可以透過安裝管理套件來延伸 System Center Operations Manager 的功能，此軟體會指示 System Center Operations Manager 可以監視的專案，以及應如何監視這些專案，以及應如何觸發預警，以及曾. Lync Server 2013 包含兩個系統中心作業管理員管理套件，可提供下列功能：

  - 元件與使用者管理套件（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）會追蹤事件日誌中記錄的 Lync Server 問題、由效能計數器註冊，或記錄在通話詳細資料記錄（CDR）或體驗品質（QoE）資料庫. 針對重要問題，系統中心作業管理員可以設定為透過電子郵件、立即訊息或短訊息服務（SMS）訊息立即通知系統管理員。 SMS 是用來將文字訊息從一部行動裝置傳送至另一部的技術。
    
    <div>
    

    > [!NOTE]  
    > 如需有關設定 Operations Manager 通知的詳細資訊，請參閱 TechNet 文件庫中<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>的 [設定通知]。

    
    </div>

  - 主動監視管理套件（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）會主動測試重要的 Lync 伺服器元件，例如登入系統、交換立即訊息，或撥打電話到公用交換的電話電話網絡（PSTN）。 這些測試是使用 Lync Server 綜合交易 Cmdlet 進行。 例如，您可以使用**Test CsIM** Cmdlet 來模擬一對測試使用者之間的立即訊息（IM）交談。 如果這個模擬的訊息交談失敗，就會產生警示。

您必須匯入管理套件。 如果您不匯入管理套件，您就無法使用 Operations Manager 來監視 Lync Server 事件或執行 Lync Server 綜合交易。

元件與使用者管理套件僅用於監視 Lync Server 2013。 如果您在共存案例中，同時已安裝 Lync Server 2013 和 Lync Server 2010，您應該繼續針對 Lync Server 2010 電腦使用 Lync Server 2010 管理套件。

<div>


> [!NOTE]  
> Lync Server 2010 的管理套件包括 Lync Server 2010 監視管理套件和 Lync Server 2010 群組聊天監視管理套件。



</div>

您可以使用下列其中一個工具匯入管理套件：

  - **System Center Operations Manager**   使用這個方法，您可以使用 Operations Manager 來新增 Lync Server 的監視。

  - **Operations manager 命令**   介面：您可以使用 operations manager shell 直接匯入，或針對您在使用 System Center Operations Manager 主控台匯入管理套件時所遇到的任何問題進行疑難排解。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 匯入管理套件

1.  下載檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。

2.  在系統中心作業管理員中，按一下 [**管理**]。

3.  在 [**管理**] 窗格中，以滑鼠右鍵按一下 [**管理套件**]，然後按一下 [匯**入管理套件**]。

4.  在 [**選取管理套件**] 對話方塊中，按一下 [**新增**]，然後按一下 [**從磁片新增**]。

5.  在 [**線上目錄連線**] 對話方塊中，按一下 [**取消**]，避免 Operations Manager 線上進行，以查看 Lync Server 管理套件是否存在任何相依性。 如果您使用的是系統中心作業管理器2012，請按一下 [**否**]。

6.  在 [**選取要匯入的管理套件**] 對話方塊中，找出並選取 [檔案] **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp**和**Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** ，然後按一下 [**開啟**]。 若要在對話方塊中選取多個檔案，請按一下第一個檔案，按住 Ctrl 鍵，然後按一下第二個檔案。

7.  在 [**選取管理套件**] 對話方塊中，按一下 [**安裝**]。 如果您收到錯誤訊息，且安裝失敗，通常表示管理套件檔案位於受 Windows 使用者帳戶控制保護的資料夾中。 如果發生這種情況，請將檔案複製到不同的資料夾，然後重新開機匯入和安裝程式。

8.  在 [**選取管理套件**] 對話方塊中，按一下 [**關閉**]。 請注意，匯入和安裝程式可能需要幾分鐘的時間才能完成。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令介面匯入管理套件

一般來說，您可以使用 [Operations Manager] 輕鬆匯入管理套件。如果發生錯誤，且匯入失敗，則主機不一定會提供足夠的錯誤報表。 依比較，Operations Manager 命令介面提供詳細資訊。 如果您使用的是 Operations Manager，且在匯入管理套件時遇到問題，請使用 Operations Manager 命令介面匯入套件。 Operations Manager 命令介面提供的詳細資訊可協助您判斷匯入失敗的原因。

如果您使用的是 System Center Operations Manager 2007 R2，請完成下列程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**系統中心作業管理器 2007 R2**]，然後按一下 [ **Operations Manager 命令**介面]。

2.  在 Operations Manager Shell 中，在命令提示字元中輸入下列命令，並使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的實際路徑，然後按 ENTER：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  匯入第一個管理套件之後，請使用您的檔案 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 複本路徑來重複此程式：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  關閉 Operations Manager 命令介面。

如果您使用系統中心作業管理器2012，請改為完成此程式：

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft System Center 2012**]，再按一下 [ **Operations Manager**]，然後按一下 [ **operations manager 命令**介面]。

2.  在 Operations Manager Shell 中，在命令提示字元中輸入下列命令，並使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的實際路徑，然後按 ENTER：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  匯入第一個管理套件之後，請使用您的檔案 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 複本路徑來重複此程式：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

