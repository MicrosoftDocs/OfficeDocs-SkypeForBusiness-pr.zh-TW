---
title: Lync Server 2013 應力和效能工具常見問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509210"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 應力和效能工具常見問題

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>常見問題集

以下是有關 Lync Server 2013 壓力和效能工具的常見問題。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生產環境中執行 LyncPerfTool.exe 嗎？

我們不建議您這麼做。 此工具會影響伺服器的效能、安全性和使用者經驗。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>我是第一次登入我的使用者。 為什麼伺服器的執行是如此高負載的？

使用者第一次登入時，會發生其他作業。 因此，Microsoft SQL Server 後端伺服器的效能將會降級。 建議您執行簡短的測試，讓您在測量結果之前，先登入所有使用者，然後重新開機用戶端。 我們不支援每秒超過12個同時使用者登入會話，但這取決於您的硬體設定。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的用戶端記憶體不足。 我該怎麼做？

如果您的用戶端記憶體不足，您必須減少每一部電腦的使用者數目。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>現在，用戶端的 CPU 都是100%。 我該怎麼做？

如果您的用戶端在所有使用者登入後都是以極高的 CPU 執行，則您必須減少每台電腦的使用者數目。 高 CPU 峰值是可接受的，但是如果有持續的，您必須減少負載。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>我是否可以在伺服器上執行此工具？

否。 這種案例不受支援，而且可能會因為二進位不符而失敗。 此外，因為點是測量伺服器上的資源消耗，所以執行工具會使度量變得無意義。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我可以在虛擬伺服器或 Microsoft Hyper-V Server 2008/2012 上執行 LyncPerfTool.exe 嗎？

是。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 的含義為何？

MPOP 代表多點顯示狀態。 這是要模擬使用者從多部機器登入 Lync 2013 的案例。 請注意，在 LyncPerfTool.exe 中，每個端點都使用預設設定檔 (也就是說，設定檔不會分割兩個存在點) 。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我已開始 LyncPerfTool.exe 但不會發生任何情況。 到底怎麼回事？

檢查用戶端上的作用中端點計數器總數，以查看使用者是否正在連線。 如果使用者未連接，請驗證您的 Lync Server 2013 設定。 發生此問題的原因通常是伺服器名稱、使用者前置詞或密碼不正確。 請注意，外部用戶端應將存取 Proxy 指定為 TargetServer 值。 驗證設定檔中的埠。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>如何知道發生什麼事？

各種 LyncPerfTool 效能計數器會指出使用者是否正在連線和執行動作。 不過，一種簡單的方法是使用 Lync 2013 登入其中一個帳戶，並執行您想要的動作。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>我已安裝 Live 迅 Server 2007 R2 容量規劃工具和/或 Lync Server 2010。 該是否正常？

否。 發生互通性問題，您必須卸載此產品所有先前的版本。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>壓力和效能工具是否會設定 CAA 的呼叫資訊伺服器拓撲？

否。 工具只會建立使用者、連絡人及通訊群組清單，並模擬使用者負載。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支援的使用者數目上限為何？

我們已建立最多80000個使用者，並使用這些工具，建立總計30000使用者的執行測試。 我們建議最多120000個使用者，但技術限制允許更高的價值，視用戶端和伺服器硬體可用而定。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

