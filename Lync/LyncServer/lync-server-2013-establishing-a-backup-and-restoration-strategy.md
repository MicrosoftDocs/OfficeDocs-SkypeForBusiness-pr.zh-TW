---
title: Lync Server 2013：建立備份與還原策略
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
ms.openlocfilehash: e281b85879063cacb9538d03fe221a4bf96b6bc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514210"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>建立 Lync Server 2013 的備份與還原策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-26_

在您開發 Lync Server 的備份與還原計劃之前，您必須開發符合組織目標的策略。 若要開發有效的備份與還原策略，您必須：

  - 建立業務優先順序。

  - 識別備份與還原的需求。

<div>

## <a name="establishing-business-priorities"></a>建立業務優先順序

評估貴組織的業務優先順序。 一般來說，影響備份和還原策略的主要業務優先順序如下：

  - 業務持續性需求

  - 資料完整性

  - 資料重要程度

  - 可攜性需求

  - 成本限制

這類業務需求，如這項協助，可判斷您為客戶開發 (Sla) 的服務等級協定。 服務等級協定會大幅影響您的備份和復原策略。

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>識別備份與還原需求

您的商務優先順序和服務等級協定會在決定組織備份及還原 Lync Server 的需求時起作用。 為下列專案識別並記錄您的需求：

  - **備份頻率**    如需有關備份頻率之最佳作法的詳細資訊，請參閱[Lync Server 2013 備份與還原的最佳作法](lync-server-2013-best-practices-for-backup-and-restoration.md)。

  - **備份及還原工具**    包含誰要使用工具，以及在哪些電腦上使用。 如需本主題所討論之工具的詳細資訊，請參閱 [Lync Server 2013 中的備份和還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。

  - **備份位置**    識別備份是否要在本機或從遠端保存，以進行安全性及可存取性考慮。 指定備份所使用的媒體。

  - **硬體和軟體需求**    識別及記錄您特定的硬體和軟體需求，包括備份儲存空間的硬體，以及支援備份及還原所需的任何軟體和網路連線能力。 當您開發硬體和軟體需求時，請牢記下列各種還原案例。

  - **還原案例**    以下是下列案例的還原程式：
    
      - Lync Server 集區失敗。 此案例需要重新構建集區中的每一部伺服器。
    
      - Standard Edition server 失敗。 此案例需要在新的或全新的電腦上重建伺服器，並還原資料庫。
    
      - 失去中央管理存放區。 此案例至少需要還原及發佈中央管理存放區。
    
      - 當中央管理存放區正常運作時，失去後端伺服器。 此案例需要在新的或全新的電腦上重建伺服器，並還原資料庫。
    
      - 屬於 Lync Server 集區成員的伺服器失敗。 此案例需要在新電腦或全新電腦上重建伺服器。
    
      - 檔存放區失敗。 此案例需要還原檔案伺服器或檔叢集。
    
      - 封存、監控或 Persistent 聊天資料庫失敗。 此案例需要重新建立資料庫，如果資料對您的組織而言很重要，請還原資料。 若要讓 Lync Server 重新備份及執行，則不需要封存、監控及持久聊天資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

