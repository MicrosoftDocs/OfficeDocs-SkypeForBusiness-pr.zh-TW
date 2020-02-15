---
title: Lync Server 2013： 安裝 Lync Server 2013 管理組件
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
ms.openlocfilehash: 2324d166ab43153cf37b71500da438e6db6b4b4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>安裝 Lync Server 2013 管理組件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

本身，System Center Operations Manager 具有監視 Windows 作業系統一小部分的能力。 不過，延伸 System Center Operations Manager 的功能，藉由安裝管理組件，即表示這項目 System Center Operations Manager 可監視的軟體，包括如何應監視這些項目，而且應該提醒方式觸發，並報告。 Microsoft Lync Server 2013 包含兩個 System Center Operations Manager 管理組件提供下列功能：

  - 元件及使用者管理組件 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 追蹤記錄在事件記錄檔、 登錄的效能計數器，或登入詳細通話記錄 (CDR) 或經驗品質 (QoE) 的 Lync Server 問題資料庫。 針對重大問題，可以設定 System Center Operations Manager 立即通知系統管理員透過電子郵件、 立即訊息，或短訊息服務 (SMS) 通訊。 SMS 是用來將文字訊息從一種行動裝置傳送到另一個技術。
    
    <div>
    

    > [!NOTE]  
    > 如需有關設定 Operations Manager 通知的詳細資訊，請參閱 TechNet Library 中的 [設定通知<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>。

    
    </div>

  - 作用中的監視組件 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主動測試重要的 Lync Server 元件，例如登入系統、 交換立即訊息，或撥打電話到位於公用交換電話電話網路 (PSTN)。 使用 Lync Server 綜合交易 cmdlet 進行這些測試。 例如， **Test-csim** cmdlet 用於模擬立即訊息交談的測試使用者對之間。 如果此模擬通訊交談失敗時就會產生警示。

Lync Server 2013 隨附的兩個管理套件管理組件與 Microsoft Lync Server 2010 搭配使用，透過包括大量的增強功能。 例如，Lync Server 2013 元件管理組件不限於監視 Lync Server 本身。 除了監控的事件記錄檔和 Lync server 的效能計數器，效能及問題警訊，例如重要項目，也可以追蹤的元件管理組件：

  - **網際網路資訊服務 (IIS)**   如果 Internet Information Services 離線，將會發出警示。 這是很重要，因為 Lync Server web services 依賴 IIS。

  - **處理程序使用**   如果系統資源 （例如可用的記憶體） 開始執行低，將會發出警示。 即使 Lync 伺服器不負責高的系統使用量，將會發出這些警示。

  - **電腦故障事件**   威脅可行性伺服器的硬體或軟體問題時，將發出警示。 例如，如果伺服器看起來可能遭遇到硬碟故障，Lync Server 系統管理員就會收到通知。

新的管理組件也功能增強型報告。 Lync Server 2013 的新報告包括：

  - **端對端案例可用性報告**   此報告詳述可用性/上線時間，例如註冊或目前狀態的 Lync Server 服務的索引鍵。

  - **容量報告**   使用效能計數器資訊，這份報告顯示系統元件，例如記憶體可用性及處理器使用量的趨勢。

  - **元件報告**   此報告會列出依 Lync Server 元件分組的首要警示產生器。

除了這些預先設計好的報告，針對 Lync Server 2013 管理組件自動報告提醒通話可靠性 （度量單位的詳細通話記錄） 及 QoE 狀態 （測量的經驗品質計量）。 如果您已啟用詳細通話記錄，您可以藉由完成下列程序，從 [System Center Operations Manager 主控台檢閱通話可靠性通知：

  - 依序展開 [**監控**依序展開 [ **Microsoft Lync Server 2013 狀況**、 展開 [**通話可靠性與媒體品質**]，然後按一下 [**通話可靠性**。

若要檢視經驗品質警示，完成此程序從 System Center Operations Manager 主控台：

  - 依序展開 [**監控**，依序展開 [ **Microsoft Lync Server 2013 狀況**、 展開 [**通話可靠性與媒體品質**]，然後展開**媒體品質**。

針對 Lync Server 2013 管理組件現在會使用機器層級探索而不是使用 Microsoft Lync Server 2010 中的集中探索機制。 這表示每個 System Center 代理程式基本上探索本身，並報告至中央管理伺服器其存在。 使用電腦層級探索簡化管理 System Center 基礎結構和也可讓不同版本的 Lync Server 管理組件 （例如，管理組件的 Lync Server 2010） 和 Lync Server 2013 管理組件共存。

</div>

<span> </span>

</div>

</div>

</div>

