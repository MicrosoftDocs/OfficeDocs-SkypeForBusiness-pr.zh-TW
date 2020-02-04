---
title: Lync Server 2013 應力與效能工具常見問題
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
ms.openlocfilehash: 9138a23ee1fa45f3da827832b568852952b0ae4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 應力與效能工具常見問題

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>常見問題

以下是 Lync Server 2013 應力和效能工具的一些常見問題。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>我可以在生產中執行 LyncPerfTool 嗎？

我們不建議您這麼做。 這個工具會影響伺服器的效能、安全性和使用者體驗。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>我是第一次登入使用者。 為什麼伺服器是以這類高負載執行？

使用者第一次登入時，會發生其他的操作。 因此，Microsoft SQL Server 後端伺服器的效能將會下降。 我們建議您執行簡短測試，以記錄所有使用者，然後重新開機用戶端，然後再測量結果。 我們每秒不支援超過12個併發使用者登入會話，但這取決於您的硬體設定。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>我的用戶端記憶體不足。 我該怎麼做？

如果用戶端記憶體不足，您必須減少每個電腦的使用者數目。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>我的客戶隨時都是100% 的 CPU。 我該怎麼做？

如果您的用戶端在所有使用者登入後都執行了極高的 CPU，您必須減少每個電腦的使用者數目。 高 CPU 峰值是可接受的，但如果持續進行，您必須減少負載。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>我可以在伺服器上執行該工具嗎？

不。 這個案例不受支援，而且可能會因為二進位不相符而失敗。 此外，因為點是測量伺服器上的資源佔用，所以執行工具時會將度量轉譯成沒有意義。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>我可以在虛擬伺服器或 Microsoft Hyper-v Server 2008/2012 上執行 LyncPerfTool 嗎？

是。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP 代表什麼意思？

MPOP 代表多個目前狀態點。 它是用來模擬使用者從多個電腦登入 Lync 2013 的情況。 請注意，在 LyncPerfTool 中，每個端點都會使用預設設定檔（也就是設定檔不會在兩個目前狀態點之間分割）。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>我已開始 LyncPerfTool，但卻沒有發生任何事。 這是怎麼回事？

檢查用戶端上的 [總作用中端點] 計數器，查看使用者是否正在連線。 如果使用者未連線，請確認您的 Lync Server 2013 設定。 這個問題通常是因為伺服器名稱、使用者的首碼或密碼不正確。 請注意，外部用戶端應該將訪問 Proxy 指定為 TargetServer 值。 驗證設定檔中的埠。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>如何知道發生了什麼事？

各種 LyncPerfTool 效能計數器會指出使用者是否要連接並執行動作。 不過，一個簡單的檢查方法是使用 Lync 2013 登入其中一個帳戶，並執行您想要的動作。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>我已安裝 [即時通訊伺服器 2007 R2 容量規劃工具] 和/或 [Lync Server 2010]。 那是確定嗎？

不。 發生互通性問題，您必須卸載此產品的所有舊版版本。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>壓力與效能工具會設定 CAA 通話資訊伺服器拓撲嗎？

不。 工具只會建立使用者、連絡人及通訊群組清單，並類比使用者負載。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>工具支援的使用者數目上限為何？

我們已建立最多80000個使用者，以及使用這些工具來總計30000個使用者所執行的測試。 我們建議您最多120000個使用者，不過，您可以根據用戶端和伺服器硬體提供的技術限制來取得較高的價值。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

