---
title: Lync Server 2013：檢查事件記錄檔
description: Lync Server 2013：檢查事件記錄檔。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570979"
---
# <a name="checking-event-logs-in-lync-server-2013"></a>在 Lync Server 2013 中檢查事件記錄檔

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-06_

您可以使用 [Windows 事件檢視器](https://go.microsoft.com/fwlink/p/?linkid=314067) 來查看事件記錄，並取得有關服務失敗的資訊、AD DS 中的複寫錯誤，以及有關系統資源（如虛擬記憶體和磁碟空間）的警告。 事件檢視器隨附于 Windows Server 2008 和2012。

在 Lync Server 2013 記錄工具中，當您結束調試會話時，請按一下 [ **分析記錄** 檔] 以使用 Snooper 工具來查看記錄檔。

事件檢視器會維護電腦上的應用程式、安全性和系統事件記錄。 Lync Server 2013 和 Windows 報告警告和錯誤狀況的事件記錄。 因此，請每天複查事件記錄。

使用事件檢視器：

  - 查看及管理事件記錄。

  - 取得必須解決之硬體、軟體及系統問題的相關資訊。

  - 識別需要未來動作的趨勢。

在 Windows Server 作業系統上執行 Lync Server 的伺服器會記錄四種記錄類型的事件：

  - **應用程式記錄**    應用程式記錄檔包含應用程式或程式所記錄的事件。 開發人員會決定要記錄的事件。 例如，資料庫程式可能會在應用程式記錄檔中記錄檔錯誤。 大部分的 Lync Server 2013 相關事件會出現在應用程式記錄檔中。

  - **安全性記錄**    除了與資源使用相關的事件（例如建立、開啟或刪除檔案或其他物件）之外，安全性記錄會記錄有效和無效登錄嘗試等事件。 例如，如果啟用登入審核，嘗試登入系統的嘗試會記錄在安全性記錄檔中。

  - **系統記錄**     檔系統記錄檔包含 Windows 系統元件所記錄的事件。 例如，在啟動期間要載入的驅動程式或其他系統元件失敗會記錄在系統記錄檔中。 由伺服器預先決定由系統元件所記錄的事件種類。

  - **Lync Server 2013**    記錄工具會記錄與驗證、連線和使用者動作相關的重大事件。 啟用診斷記錄後，您可以在事件檢視器中查看記錄專案。

<div>


> [!NOTE]  
> 建議您不要使用最大記錄設定，除非您是由 Microsoft 客戶支援服務指示您這麼做。 記錄消耗大量資源，而且可能會提供許多 "誤報"，也就是在最大記錄中記錄的錯誤，但實際上卻是預期的，而不是問題的原因。 我們也建議您不要永久啟用診斷記錄。 請僅在疑難排解時使用。



</div>

在每個事件檢視器記錄中，Lync Server 2013 記錄資訊性、警告和錯誤事件。 請密切監視這些記錄，以追蹤在 Lync Server 2013 伺服器上進行的交易類型。 您應該定期封存記錄檔或使用自動滾動更新，以避免空間不足。 因為記錄檔可以佔用有限的空間，所以請將記錄檔大小 (增加為 50 MB) 並設定為覆寫，這樣 Lync Server 2013 伺服器便可以繼續撰寫新的事件。

您也可以使用下列工具和技術來自動化事件記錄管理：

  - System Center Operations Manager 會監視 Lync Server 2013 伺服器的健康情況和使用狀況。 Lync Server 2013 管理元件，可讓 Operations manager 擴充 Operations Manager，其為執行 Lync Server 2013 的伺服器提供專用監控。

  - Operations Manager 的 Lync Server 2013 管理元件會監控 Lync Server 2013 的 Standard 和 Enterprise Edition。 此版本也包含先前為個別管理元件的 (QoE) 管理套件的經驗品質。

受監視類型為事件記錄專案、效能計數器及 QoE 的監控狀態。 這個版本的管理套件只會監視 Lync Server 2013 和2010，而且無法用來監視 Office 通訊伺服器2007。

管理元件提供下列功能：

  - 警示指出服務影響事件

  - 指出設定和其他非服務影響問題的警示

  - Lync Server 服務的狀態監控

  - 產品知識：發現問題的原因和解決方法

如需 Lync Server 2013 管理元件的詳細資訊，請參閱 [使用 System Center Operations Manager 監視 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。

**事件梳紋**    事件梳紋工具會將多部電腦之事件記錄檔中的特定事件，從一個集中位置收集。 它可讓您僅報告其所指定的事件 IDs 或事件來源。 如需事件梳紋的詳細資訊，請參閱 [帳戶鎖定和管理工具](https://go.microsoft.com/fwlink/?linkid=35607) 網站。

**事件觸發器**    在 Windows Server 2012 中，您可以在 Windows 事件檢視器中「將工作附加到這個事件」，讓系統管理員可以執行程式、傳送電子郵件訊息或顯示幕幕郵件。 如需此功能的相關資訊，請參閱 Windows Server 2008 R2 主題 [執行工作以回應指定的事件](https://technet.microsoft.com/library/cc748900.aspx)。 您也可以使用命令列工具（如 ' Eventtrigger.exe '）來建立及查詢事件記錄，並將程式與特定記錄的事件關聯。 透過使用 Eventtriggers.exe，您可以建立在特定事件發生時執行程式的事件觸發器。

<div>

## <a name="see-also"></a>另請參閱


[Windows 事件檢視器](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

