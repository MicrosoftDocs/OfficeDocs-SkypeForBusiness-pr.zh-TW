---
title: Lync Server 2013：建立備份及還原策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>建立 Lync Server 2013 的備份與還原策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

在您可以為 Lync Server 開發備份和還原方案之前，您必須開發符合貴組織目標的戰略。 若要開發有效的備份和還原策略，您必須：

  - 建立業務優先順序。

  - 找出備份和還原需求。

<div>

## <a name="establishing-business-priorities"></a>建立業務優先順序

評估貴組織的業務優先順序。 通常會影響您備份和還原策略的主要業務優先順序如下所示：

  - 業務連續性需求

  - 資料完整性

  - 資料重要程度

  - 便攜性需求

  - 成本限制

如以下所述的商業需求，這些說明可判斷您與客戶一起開發的服務等級協定（Sla）。 服務層級協定會大大影響您的備份與復原策略。

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>識別備份和還原需求

您的業務優先順序與服務等級協定會在判斷貴組織對備份和還原 Lync Server 的需求時起作用。 針對下列專案，找出並記錄您的需求：

  - **備份頻率如**   需有關備份頻率之最佳做法的詳細資料，請參閱[Lync Server 2013 備份和還原的最佳做法](lync-server-2013-best-practices-for-backup-and-restoration.md)。

  - **備份和還原工具**   包括誰是要使用工具的人員，以及在哪些電腦上。 如需本主題中討論的工具及必要許可權的詳細資訊，請參閱[Lync Server 2013 中的備份與還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。

  - **[備份位置**   ] 找出備份是在本機或遠端保留，並考慮安全性及協助工具。 指定要用於備份的媒體。

  - **硬體和軟體需求**   可識別並記錄您的特定硬體和軟體需求，包括備份儲存空間的硬體及特定元件的還原，以及支援備份和還原所需的任何軟體和網路連線。 隨著您開發硬體和軟體需求，請記住下列各種不同的還原案例。

  - **還原案例**   以下是下列案例的還原程式：
    
      - Lync 伺服器池失敗。 這個案例需要重建池中的每個伺服器。
    
      - 標準版伺服器無法使用。 這個案例需要在新的或乾淨的電腦上重建伺服器，並還原資料庫。
    
      - 中央管理儲存區遺失。 這個案例至少需要還原併發布中央管理儲存體。
    
      - 中央管理儲存仍正常運作時，後端伺服器遺失。 這個案例需要在新的或乾淨的電腦上重建伺服器，並還原資料庫。
    
      - 成為 Lync 伺服器池成員的伺服器失敗。 這個案例需要在新的或乾淨的電腦上重建伺服器。
    
      - 檔案儲存區失敗。 這個案例需要還原檔案伺服器或檔案群集。
    
      - [封存]、[監視] 或 [永久聊天] 資料庫失敗。 這個案例需要重新建立資料庫，如果資料對您的組織是重要的，請還原資料。 [封存]、[監視] 和 [持續聊天] 資料不需要讓 Lync Server 重新開機並執行。

</div>

</div>

<span> </span>

</div>

</div>

</div>

