---
title: Lync Server 2013 壓力及效能工具常見問題集
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
ms.openlocfilehash: f6c4a9909bfecd8157fe3afe9f653a684fe1053b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 壓力及效能工具常見問題集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

<div>

## <a name="frequently-asked-questions"></a>常見問題集

以下是一些常見問題的 Lync Server 2013 壓力及效能工具。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>可以在生產環境中執行 LyncPerfTool.exe 嗎？

我們不建議這。 此工具會影響伺服器效能、 安全性及使用者體驗。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>我已經在第一次登入我的使用者。 為什麼的伺服器會在這類高負載執行？

第一次使用者登入，有發生的其他作業。 因此，在 Microsoft SQL Server 後端伺服器上的效能會降低。 我們建議您執行的簡短的測試，記錄上的所有使用者，並之前測量結果，然後重新啟動用戶端。 我們不支援超過 12 個並行使用者登入工作階段，每秒，但這取決於您的硬體設定。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的用戶端都執行記憶體不足。 我該怎麼辦？

如果您的用戶端都執行記憶體不足，您需要降低每部電腦的使用者數目。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>我的用戶端在都是 100%的 cpu 使用量所有的時間。 我該怎麼辦？

如果您的用戶端執行極高的 CPU 與所有使用者已都登入之後，您需要降低每部電腦的使用者數目。 高 CPU 突發性都可接受的但如果它承受，您需要降低的負載。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>可在本身的伺服器上執行工具？

否。 此案例中不受支援，而且由於二進位不符可能會失敗。 此外，由於點是測量伺服器上的資源消耗量，那里執行此工具會轉譯度量單位從沒有意義。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>虛擬伺服器上或在 Microsoft HYPER-V Server 2008/2012年可以執行 LyncPerfTool.exe 嗎？

是。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 是什麼意思？

MPOP 代表多個存在點。 它是用來模擬其中使用者已登入 Lync 2013 從多部電腦的案例。 請注意，在 LyncPerfTool.exe，每個端點會使用預設的設定檔 （也就是設定檔不會分割之間的目前狀態的兩個點）。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我開始 LyncPerfTool.exe 但 nothing 的情形。 到底怎麼回事？

請檢查以查看使用者是否所連線之用戶端上的總作用中的端點計數器。 如果使用者未連線，請確認您的 Lync Server 2013 設定。 因為伺服器名稱、 使用者前置詞或密碼不正確，通常就會發生這個問題。 請注意外部用戶端為 TargetServer 值，指定 Access Proxy。 確認組態檔中的連接埠。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>如何知道某個項目的情形？

各種 LyncPerfTool 效能計數器指出使用者連線並執行的動作。 不過，簡單的方法來檢查是登入帳戶的其中一個使用 Lync 2013，並執行您想要的動作。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>我有 Live Communications Server 2007 R2 的容量規劃工具及/或 Lync Server 2010 安裝。 這是確定嗎？

否。 互通性問題，您必須先解除安裝所有舊版的這項產品。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>會設定 CAA 通話資訊伺服器拓撲的壓力及效能工具？

否。 工具只會建立使用者、 連絡人和通訊群組清單及模擬使用者負載。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支援的使用者數目上限為何？

我們已建立合計 80000 位使用者最多，並執行測試加總 30000 位使用者，使用這些工具。 雖然技術限制允許較高的值，根據可用的用戶端和伺服器硬體，建議最大值為 120000 使用者。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

