---
title: Lync Server 2013：匯入 Lync Server 2013 管理套件
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
ms.openlocfilehash: 4edc22c1cfc46b032e679a9dc0718113bc6967bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526650"
---
# <a name="importing-the-lync-server-2013-management-packs"></a>匯入 Lync Server 2013 管理套件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

您可以安裝管理套件（會決定 System Center Operations Manager 可監控哪些專案，以及應如何監視和報告警報）的軟體，以擴充 System Center Operations Manager 的功能。 Lync Server 2013 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：

  - Component 和 User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤事件記錄檔中記錄的 Lync Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (CDR) 或經驗品質 (QoE) 資料庫。 針對嚴重問題，System Center Operations Manager 可以設定為透過電子郵件、立即訊息或短訊息服務立即通知系統管理員 (SMS) 訊息。 SMS 是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。 ) 
    
    <div>
    

    > [!NOTE]  
    > 如需設定 Operations Manager 通知的詳細資訊，請參閱設定 TechNet 程式庫中的通知 <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> 。

    
    </div>

  - 主動監控管理元件 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。 使用 Lync Server 綜合交易 Cmdlet 進行這些測試。 例如，您可以使用 **Test-CsIM** Cmdlet 來模擬一對測試使用者之間的立即訊息 (IM) 交談。 如果此模擬的郵件交談失敗，則會產生警示。

您必須匯入管理套件。 若不匯入管理套件，則無法使用 Operations Manager 來監視 Lync Server 事件或執行 Lync Server 綜合交易。

元件和使用者管理套件只會用來監視 Lync Server 2013。 如果您處於共存案例中，且同時安裝了 Lync Server 2013 和 Lync Server 2010，則應該繼續使用 lync server 2010 管理套件進行 Lync Server 2010 電腦。

<div>


> [!NOTE]  
> Lync Server 2010 的管理元件包括 Lync Server 2010 Monitoring Management Pack 和 Lync Server 2010 Group Chat Monitoring Management Pack。



</div>

您可以使用下列其中一個工具匯入管理元件：

  - **System Center Operations Manager**    使用此方法，您可以使用 Operations Manager 來新增監控的 Lync Server。

  - **Operations Manager 命令**     介面您可以使用 Operations Manager 命令介面直接匯入，或疑難排解您使用 System Center Operations Manager 主控台匯入管理元件時所遇到的任何問題。

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>使用 System Center Operations Manager 匯入管理套件

1.  下載檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。

2.  在 System Center Operations Manager 中，按一下 [ **管理**]。

3.  在 [ **管理** ] 窗格中，以滑鼠右鍵按一下 [ **管理元件**]，然後按一下 [匯 **入管理元件**]。

4.  在 [ **選取管理元件** ] 對話方塊中，按一下 [ **新增**]，然後按一下 [ **從磁片新增**]。

5.  在 [ **線上目錄連線** ] 對話方塊中，按一下 [ **取消** ]，以防止 Operations Manager 進入線上狀態，以查看是否存在 Lync Server 管理套件的任何相依性。 如果您使用 System Center Operations Manager 2012，請按一下 [ **否**]。

6.  在 [ **選取要匯入的管理元件** ] 對話方塊中，找出並選取 **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** 及 **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** 的檔案，然後按一下 [ **開啟**]。 若要在對話方塊中選取多個檔案，請按一下第一個檔案，按住 Ctrl 鍵，然後按一下第二個檔案。

7.  在 [ **選取管理元件** ] 對話方塊中，按一下 [ **安裝**]。 如果您收到錯誤訊息，且安裝失敗，這通常表示管理元件檔案位於由 Windows 使用者帳戶控制保護的資料夾中。 如果發生這種情況，請將檔案複製到其他資料夾，然後重新開機匯入和安裝程式。

8.  在 [ **選取管理元件** ] 對話方塊中，按一下 [ **關閉**]。 請注意，匯入和安裝程式可能需要數分鐘才能完成。

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>使用 Operations Manager 命令介面匯入管理元件

一般來說，使用 Operations Manager 匯入管理元件時，會比較容易。不過，如果發生錯誤，且匯入失敗，則主控台不一定會提供適當的錯誤報表。 依比較，Operations Manager 命令介面會提供詳細資訊。 如果您使用的是 Operations Manager，而且在匯入管理元件時遇到問題，請使用 Operations Manager 命令介面匯入套裝軟體。 Operations Manager 命令介面提供更多資訊，可協助您判斷匯入失敗的原因。

如果您使用的是 System Center Operations Manager 2007 R2，請完成下列程式：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **System Center Operations Manager 2007 R2**]，然後按一下 [ **Operations Manager 命令**介面]。

2.  在 Operations Manager 命令介面中，使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  在匯入第一個管理套件之後，請使用檔案副本的路徑重複處理常式 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp：
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  關閉 Operations Manager 命令介面。

如果您使用 System Center Operations Manager 2012，請改為完成此程式：

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft System Center 2012**] 及 [ **Operations Manager**]，然後按一下 [ **operations manager 命令**介面]。

2.  在 Operations Manager 命令介面中，使用檔案 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的實際路徑，在命令提示字元處輸入下列命令，然後按 ENTER：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  在匯入第一個管理套件之後，請使用檔案副本的路徑重複處理常式 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp：
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

