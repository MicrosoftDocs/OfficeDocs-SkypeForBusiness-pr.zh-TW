---
title: Lync Server 2013：檢查事件記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>在 Lync Server 2013 中檢查事件記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-06_

您可以使用[Windows 事件檢視器](http://go.microsoft.com/fwlink/p/?linkid=314067)來查看事件記錄，並取得服務失敗的相關資訊、AD DS 中的複製錯誤，以及有關系統資源（例如虛擬記憶體和磁碟空間）的警告。 [事件檢視器] 包含在 Windows Server 2008 和2012中。

在 Lync Server 2013 記錄工具中，當您結束調試會話時，請按一下 [**分析記錄**檔]，透過使用 Snooper 工具來查看記錄檔。

事件檢視器可維護電腦上的應用程式、安全性及系統事件的相關記錄。 [Lync Server 2013] 和 [Windows] 都會向事件記錄中報告警告和錯誤情況。 因此，請每天查看事件記錄。

使用事件檢視器進行下列作業：

  - 查看和管理事件記錄。

  - 取得必須解決之硬體、軟體及系統問題的相關資訊。

  - 找出需要後續動作的趨勢。

在 Windows 伺服器作業系統上執行 Lync Server 的伺服器會在四種類型的記錄中記錄事件：

  - **應用程式記錄**   應用程式記錄包含應用程式或程式所記錄的事件。 開發人員決定要記錄哪些事件。 例如，資料庫程式可能會在應用程式記錄檔中記錄檔案錯誤。 大多數 Lync Server 2013 相關事件都會出現在應用程式記錄中。

  - **安全性**記錄（除了建立、開啟或刪除檔案或其他物件等與資源使用相關的事件以外，安全性記錄（例如有效和不正確登錄嘗試）也會記錄事件。    例如，如果已啟用登入審核，則會將嘗試登入系統的嘗試記錄在安全性記錄中。

  - **系統記錄**   系統記錄包含 Windows 系統元件所記錄的事件。 例如，在啟動期間，要載入的驅動程式或其他系統元件失敗，會記錄在系統記錄中。 系統元件所記錄的事件種類是由伺服器預先確定。

  - **Lync Server 2013**   記錄工具會記錄與驗證、連線及使用者動作相關的重要事件。 啟用診斷記錄之後，您可以在事件檢視器中查看記錄專案。

<div>


> [!NOTE]  
> 我們不建議您使用 [最大記錄] 設定，除非您是由 Microsoft 客戶支援服務指示您執行此動作。 消耗大量資源的最大記錄數，而且可能會有多個 "誤報"，也就是，只會記錄最大記錄，但實際預期的錯誤，而不是考慮問題的原因。 我們也建議您不要永久啟用診斷記錄。 只有在進行疑難排解時才使用它。



</div>

在每個事件檢視器記錄中，Lync Server 2013 會記錄資訊、警告和錯誤事件。 密切監視這些記錄，以追蹤要在 Lync Server 2013 伺服器上執行的交易類型。 您應該定期封存記錄，或使用自動滾動更新來避免空間不足。 因為記錄檔案可能佔用有限數量的空間，增加記錄大小（例如，到 50 MB），並將它設為 [覆寫]，讓 Lync Server 2013 伺服器可以繼續寫入新的事件。

您也可以使用下列工具和技術，自動執行事件記錄管理：

  - System Center Operations Manager 會監視 Lync Server 2013 伺服器的健康情況和使用方式。 Operations Manager 的 Lync Server 2013 管理套件會針對執行 Lync Server 2013 的伺服器提供專用的監視，擴大作業管理員。

  - Operations Manager 的 Lync Server 2013 管理套件會監視 Lync Server 2013 的標準版和企業版。 這個版本也包含先前是獨立管理套件的體驗品質（QoE）管理套件。

受監視的類型是事件記錄專案、效能計數器及 QoE 的狀態監視。 這個版本的管理套件只會監視 Lync Server 2013 和2010，且無法用來監視 Office 通訊伺服器2007。

管理套件提供下列功能：

  - 警示，指出服務影響事件

  - 代表設定的警示，以及其他未服務影響的問題

  - Lync Server services 的狀態監視

  - 產品知識：發現問題的原因及解決方式

如需 Lync Server 2013 管理套件的詳細資訊，請參閱[使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。

**事件組合**   事件組合工具會將多個電腦的事件記錄中的特定事件收集到一個中央位置。 它可讓您只報告事件識別碼或它所指定的事件來源。 如需事件組合的詳細資訊，請參閱[帳戶封鎖與管理工具](http://go.microsoft.com/fwlink/?linkid=35607)網站。

****    Windows Server 2012 中的事件觸發程式：您可以在 windows 事件檢視器中 "將工作附加至此活動]，讓系統管理員可以執行程式、傳送電子郵件訊息或顯示幕幕上的訊息。 如需此功能的詳細資訊，請參閱 Windows Server 2008 R2 主題[執行工作以回應指定事件](http://technet.microsoft.com/en-us/library/cc748900.aspx)。 您也可以使用命令列工具（例如 "Eventtrigger"）來建立及查詢事件記錄，並將程式與特定的記錄事件建立關聯。 使用 Eventtriggers，您可以建立在特定事件發生時執行程式的事件觸發程式。

<div>

## <a name="see-also"></a>請參閱


[Windows 事件檢視器](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

