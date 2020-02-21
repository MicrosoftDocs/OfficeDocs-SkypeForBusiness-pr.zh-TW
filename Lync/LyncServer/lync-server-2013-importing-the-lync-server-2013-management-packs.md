---
title: Lync Server 2013： 匯入 Lync Server 2013 管理組件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd5f09d80aa86c9c0f692fbe0e744a445067e74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>匯入 Lync Server 2013 管理組件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

您可以藉由安裝管理組件擴充功能的 System Center Operations Manager — 軟體，即表示這項目 System Center Operations Manager 可監視、 如何應監視這些項目並觸發提醒的方式和報告。 Lync Server 2013 包含兩個 System Center Operations Manager 管理組件提供下列功能：

  - 元件及使用者管理組件 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤記錄在事件記錄檔、 登錄的效能計數器，或登入詳細通話記錄 (CDR) 或經驗品質 (QoE) 的 Lync Server 問題資料庫。 針對重大問題，可以設定 System Center Operations Manager 立即通知系統管理員透過電子郵件、 立即訊息，或短訊息服務 (SMS) 通訊。 SMS 是用來將文字訊息從一種行動裝置傳送到另一個技術）。
    
    <div>
    

    > [!NOTE]  
    > 如需設定 Operations Manager 通知的詳細資訊，請參閱 TechNet Library 「 設定通知<A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>。

    
    </div>

  - 作用中監控管理組件 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、 交換立即訊息，或撥打電話到位於公用交換電話電話網路 (PSTN)。 使用 Lync Server 綜合交易 cmdlet 進行這些測試。 例如，您可以使用**Test-csim**指令程式以模擬立即訊息 (IM) 交談的測試使用者對之間。 如果此模擬的訊息對話失敗警示產生。

您必須匯入管理組件。 如果您不要匯入管理組件，您無法使用 Operations Manager 監視 Lync Server 的事件，或執行 Lync Server 綜合交易。

使用者管理組件與元件只用來監視 Lync Server 2013 中。 如果您是在共存案例中，其中有 Lync Server 2013 和 Lync Server 2010 安裝，您應繼續使用 Lync Server 2010 管理組件的 Lync Server 2010 電腦。

<div>


> [!NOTE]  
> 適用於 Lync Server 2010 管理組件包含 Lync Server 2010 Monitoring Management Pack 及 Lync Server 2010 群組聊天監控管理組件。



</div>

您可以使用下列其中一個下列工具匯入管理組件：

  - **System Center Operations Manager**   使用此方法之後，您可以使用 Operations Manager 新增 Lync Server 的監視。

  - **Operations Manager 殼層**   直接匯入或您使用 System Center Operations Manager 主控台匯入管理組件時，發生任何問題進行疑難排解，您可以使用 Operations Manager 殼層。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 匯入管理組件

1.  下載 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 及 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 兩個檔案。

2.  在 System Center Operations Manager，按一下 [**管理**]。

3.  在 [**管理**] 窗格中，以滑鼠右鍵按一下 [**管理組件**，，，然後按一下 [**匯入管理組件**。

4.  在 [**選取管理組件**] 對話方塊中，按一下 [**新增**]，然後按一下 [**從磁碟新增]**。

5.  在 [**線上目錄連線**] 對話方塊中，按一下 [**取消**] 以防止 Operations Manager 移 online，請參閱針對 Lync Server 管理組件若存在任何相依性。 如果您使用 System Center Operations Manager 2012，按一下 [**否]**。

6.  在 [**選取要匯入管理組件**] 對話方塊中，尋找和選取**Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp**及**Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**兩個檔案，然後按一下**開啟**。 若要選取多個檔案] 對話方塊中，按一下 [第一個檔案，按住 Ctrl 鍵，然後按一下第二個檔案。

7.  在 [**選取管理組件**] 對話方塊中，按一下 [**安裝**]。 如果您收到錯誤訊息，安裝就會失敗，，通常表示管理組件檔案在受保護的 Windows 使用者帳戶控制] 資料夾。 如果發生這種情況，將檔案複製到不同的資料夾，然後重新啟動匯入並安裝程序。

8.  在 [**選取管理組件**] 對話方塊中，按一下 [**關閉**]。 請注意的匯入和安裝程序可能需要數分鐘才能完成。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 殼層匯入管理組件

一般會比較容易使用作業 Manager.However 中，如果發生錯誤，而且匯入失敗時，主控台一律也不會提供足夠的錯誤報告匯入管理組件。 相較之下，Operations Manager 命令介面中，提供詳細的資訊。 如果您使用 Operations Manager，而且您遇到匯入管理組件，匯入組件，以使用 Operations Manager 命令介面。 Operations Manager 殼層提供可協助您判斷匯入失敗的原因的詳細資訊。

如果您使用 System Center Operations Manager 2007 R2，請完成下列程序：

1.  按一下 [**開始]**、 [**所有程式]**、 [ **System Center Operations Manager 2007 R2**，，然後按一下**Operations Manager 殼層**。

2.  在 Operations Manager 命令介面中，在命令提示字元處使用 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp，檔案副本的實際路徑輸入下列命令，然後按 ENTER:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  匯入第一個管理組件後，重複進行這個程序，使用 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 檔案的路徑：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  關閉 Operations Manager 殼層。

如果您使用 System Center Operations Manager 2012，請改為完成此程序：

1.  按一下 [**開始]**、 [**所有程式]**、 按一下 [ **Microsoft System Center 2012**，按一下**Operations Manager**]，然後按一下**Operations Manager 殼層**。

2.  在 Operations Manager 命令介面中，在命令提示字元處使用 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp，檔案副本的實際路徑輸入下列命令，然後按 ENTER:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  您已匯入第一個管理組件後，重複使用 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 檔案的路徑的程序：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

