---
title: Lync Server 2013：安裝 Lync Server 2013 管理套件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>安裝 Lync Server 2013 管理套件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

系統中心作業管理員本身只能監視 Windows 作業系統的一小部分。 不過，您可以透過安裝管理套件、軟體來決定系統中心作業管理員可以監視的專案，包括如何監視這些專案，以及應如何進行提醒，來延伸 System Center Operations Manager 的功能已觸發並報告。 Microsoft Lync Server 2013 包含兩個系統中心作業管理員管理套件，可提供下列功能：

  - 元件與使用者管理套件（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）會追蹤事件日誌中記錄的 Lync Server 問題、由效能計數器註冊，或記錄在通話詳細資料記錄（CDR）或體驗品質（QoE）資料庫. 針對重要問題，系統中心作業管理員可以設定為透過電子郵件、立即訊息或短訊息服務（SMS）訊息立即通知系統管理員。 SMS 是用來將文字訊息從一部行動裝置傳送至另一部的技術。
    
    <div>
    

    > [!NOTE]  
    > 如需有關設定 Operations Manager 通知的詳細資訊，請參閱 TechNet Library 中的<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>[設定通知]。

    
    </div>

  - 主動監視套件（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）會主動測試重要的 Lync 伺服器元件，例如登入系統、交換立即訊息，或撥打電話至位於公用切換電話上的電話網路（PSTN）。 這些測試是使用 Lync Server 綜合交易 Cmdlet 進行。 例如， **CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。 如果這個模擬的訊息交談失敗，就會產生警示。

Lync Server 2013 隨附的兩個管理套件包含大量針對 Microsoft Lync Server 2010 所使用之管理套件的增強功能。 例如，Lync Server 2013 元件管理套件不限於監視 Lync Server 本身。 除了監視 Lync Server 的事件記錄和效能計數器之外，元件管理套件也可以追蹤重要專案的效能及發出警示，例如：

  - ****    如果網際網路資訊服務離線，就會發出網際網路資訊服務（IIS）通知。 這很重要，因為 Lync Server web 服務依賴 IIS。

  - ****    如果系統資源（例如可用記憶體）開始不足，就會發出 [處理常式使用量] 警示。 即使 Lync 伺服器不負責高系統使用量，也會發出這些通知。

  - ****    如果硬體或軟體問題威脅伺服器的生存能力，就會發出 [電腦失敗事件] 警示。 例如，如果伺服器似乎有遇到硬碟故障的危險，就會通知 Lync Server 系統管理員。

新的管理套件也提供增強的報告功能。 Lync Server 2013 的新報告包括：

  - **端對端案例可用性報告**   此報告詳細說明主要 Lync 伺服器服務（例如註冊或目前狀態）的可用性/正常運作時間。

  - **容量報告**   使用效能計數器資訊，此報告會顯示系統元件（例如記憶體可用性與處理器使用量）的趨勢。

  - **元件報告**   ：此報告會列出依 Lync Server 元件分組的上方警示發生器。

除了這些預先設計的報表之外，Lync Server 2013 的管理套件也會自動報告通話可靠性（依通話詳細資料記錄來度量）與 QoE 狀態（依經驗品質衡量）的警示。 如果您已啟用 [通話詳細資料錄製]，您可以透過 [System Center Operations Manager] 主控台完成下列程式，查看 [通話可靠性警報]：

  - 展開 [**監視**]，展開 [ **Microsoft Lync Server 2013 健康情況**]，展開 [**通話可靠性及媒體質量**]，然後按一下 [**通話可靠性**]。

若要查看體驗警報的品質，請從 System Center Operations Manager 主控台完成此程式：

  - 展開 [**監視**]，展開 [ **Microsoft Lync Server 2013 健康情況**]，展開 [**通話可靠性及媒體質量**]，然後展開 [**媒體質量**]。

Lync Server 2013 的管理套件現在使用電腦層級探索，而不是使用 Microsoft Lync Server 2010 中的中央探索機制。 這表示每個系統中心代理本質都會自行探索，並報告它在中央管理伺服器中存在的情況。 使用電腦層級探索可簡化系統中心基礎結構的管理，也允許不同版本的 Lync Server 管理套件（例如，Lync Server 2010 的管理套件和 Lync Server 2013 的管理套件）可彼此.

</div>

<span> </span>

</div>

</div>

</div>

