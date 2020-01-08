---
title: Lync Server 2013：適用于核心基礎結構的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Lync Server 2013 中核心基礎結構的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-27_

您可能已經採取步驟，在您的系統中設計容錯能力，例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施，以及監視伺服器活動。 這些做法不僅能獲益您的 Microsoft Lync Server 2013 基礎結構，還能受益于整個網路。 如果您尚未實現這些做法，建議您在部署 Lync Server 2013 之前先執行此動作。

若要協助保護 Lync Server 2013 部署中的伺服器不受意外或 purposeful 損害，可能會導致宕機，請採取下列預防措施：

  - 使用安全性更新讓伺服器保持在最新狀態。 訂閱 Microsoft Security Notification 服務可協助確保您立即收到任何 Microsoft 產品的安全公告版本通知。 若要訂閱，請移至 Microsoft 技術安全性通知網站[http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)：。

  - 確定正確設定存取權限。

  - 讓您的伺服器保持在可避免未經授權存取的實體環境中。 確保您的所有伺服器都安裝了適當的防毒軟體。 使用最新的病毒簽名檔案，讓軟體保持在最新狀態。 使用防病毒應用程式的自動更新功能，將病毒簽名保持在最新狀態。

  - 我們建議您停用安裝 Lync Server 2013 之電腦上不需要的 Windows Server 作業系統服務。

  - 在儲存資料時使用完整容量加密系統來加密作業系統與磁片磁碟機，除非您能保證對伺服器的持續及完整控制、總物理隔離性，以及適當且安全地解除取代或失敗的磁片促進.

  - 停用伺服器的所有外部直接記憶體存取（DMA）埠，除非您能保證嚴格控制伺服器的物理存取權。 DMA （可以相當輕鬆地啟動）的攻擊會公開非常敏感的資訊，例如私人加密金鑰。

</div>

<span> </span>

</div>

</div>

</div>

