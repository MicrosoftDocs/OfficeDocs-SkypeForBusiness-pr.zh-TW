---
title: Lync Server 2013：安裝 Lync Server 2013 管理元件
description: Lync Server 2013：安裝 Lync Server 2013 管理元件套件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb50146474211c12dbd95801ed2b20f6bbfd8c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573829"
---
# <a name="installing-the-lync-server-2013-management-packs"></a>安裝 Lync Server 2013 管理套件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

System Center Operations Manager 本身只會能夠監控一小部分的 Windows 作業系統。 不過，您可以安裝管理套件（會決定 System Center Operations Manager 可監控哪些專案，包括應如何監視哪些專案，以及如何觸發和報告提醒），以擴充 System Center Operations Manager 的功能。 Microsoft Lync Server 2013 包括兩個 System Center Operations Manager 管理元件，可提供下列功能：

  - Component 和 User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤事件記錄檔中記錄的 Lync Server 問題、由效能計數器所註冊，或是記錄在詳細通話記錄 (CDR) 或經驗品質 (QoE) 資料庫。 針對嚴重問題，System Center Operations Manager 可以設定為透過電子郵件、立即訊息或短訊息服務立即通知系統管理員 (SMS) 訊息。 SMS 是用來將文字訊息從一部行動裝置傳送至另一部行動裝置的技術。
    
    <div>
    

    > [!NOTE]  
    > 如需設定 Operations Manager 通知的詳細資訊，請參閱設定 TechNet 文件庫中的通知 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A> 。

    
    </div>

  - Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、交換立即訊息，或撥打位於公用交換電話網路 (PSTN) 的電話。 使用 Lync Server 綜合交易 Cmdlet 進行這些測試。 例如， **Test-CsIM** Cmdlet 是用來模擬一對測試使用者之間的立即訊息交談。 如果此模擬的郵件交談失敗，就會產生警示。

Lync Server 2013 隨附的兩個管理元件，包含與 Microsoft Lync Server 2010 搭配使用之管理套件的大量增強功能。 例如，Lync Server 2013 元件管理元件不局限于監視 Lync Server 本身。 除了監視 Lync Server 的事件記錄檔和效能計數器之外，元件管理套件也可以追蹤重要專案的效能及發出警示，例如：

  - **Internet Information Services (IIS) **    如果網際網路資訊服務離線，就會發出警示。 這一點很重要，因為 Lync Server web 服務依賴 IIS。

  - **進程使用**    如果系統資源 (例如可用記憶體) 開始不足，就會發出警示。 即使 Lync Server 不負責高系統使用量，也會發出這些警示。

  - **電腦失敗事件**    當硬體或軟體問題威脅伺服器的活力時，就會發出警示。 例如，如果伺服器似乎是出現硬碟失敗的危險，就會通知 Lync Server 管理員。

新管理套件也提供增強型報告功能。 Lync Server 2013 的新報告包括：

  - **端對端案例可用性報告**    此報表詳述主要 Lync Server 服務（如註冊或目前狀態）的可用性/運作時間。

  - **容量報告**    此報告使用效能計數器資訊，顯示系統元件的趨勢，例如記憶體可用性及處理器使用量。

  - **元件報告**    這份報告會列出排名依 Lync Server 元件分組的上方警示發生器。

除了這些預先設計的報告之外，Lync Server 2013 的管理元件也會自動報告通話可靠性 (度量單位) 和 QoE 狀態， (以經驗品質) 衡量的統計資料。 如果您已啟用詳細通話記錄，您可以從 System Center Operations Manager 主控台完成下列程式，以查看通話可靠性警示：

  - 依序展開 [ **監視**]、[ **Microsoft Lync Server 2013 狀況**]、[ **通話可靠性與媒體質量**]，然後按一下 [ **通話可靠性**]。

若要查看經驗品質警示，請從 System Center Operations Manager 主控台完成此步驟：

  - 依序展開 [ **監視**]、[ **Microsoft Lync Server 2013 狀況**]、[ **通話可靠性與媒體質量**]，然後展開 [ **媒體質量**]。

Lync Server 2013 的管理元件現在使用電腦層級探索，而不是 Microsoft Lync Server 2010 中所用的中央探索機制。 這表示每個 System Center agent 實質上會自行探索，並報告其是否存在於中央管理伺服器。 使用電腦層級探索可簡化系統中心基礎結構的管理，也允許不同版本的 Lync Server 管理套件 (例如，lync Server 2010 的管理套件和 Lync Server 2013 的管理套件可共存) 。

</div>

<span> </span>

</div>

</div>

</div>

