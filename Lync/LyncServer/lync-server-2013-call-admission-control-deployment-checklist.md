---
title: Lync Server 2013：呼叫許可控制部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的呼叫許可控制部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

使用下列檢查清單來確認您已完成所有必要的設定工作，以部署呼叫許可控制（CAC）。

  - 如果一或多個邊緣伺服器已部署，則必須將每個外部介面 IP 位址新增到 [網路設定] 中的子網清單中，位元遮罩為32。 您也應該將這個子網（IP 位址）與「A/V Edge」服務所部署之地理位置的 [網路 site ID] 建立關聯。
    
    <div>
    

    > [!NOTE]  
    > Edge 伺服器不是實現 CAC 所必需的。

    
    </div>

  - 確認 CAC 已啟用，不論是透過 Lync Server [控制台]，或是執行在[Lync server 2013 的 [啟用呼叫許可控制](lync-server-2013-enable-call-admission-control.md)] 中指定的 Cmdlet。

  - 確定所有中央網站都已啟用 CAC。 這可以透過拓撲產生器完成。 如果您發佈時產生警告，*請勿*忽略。

  - 確認在商業網路中管理的所有子網都已設定在 [網路設定] 中。 在[Lync Server 2013 中將子網與網路網站建立](lync-server-2013-associate-a-subnet-with-a-network-site.md)關聯，也必須將每個子網與網路網站相關聯。

  - 確定所有前端伺服器、Survivable 分支裝置（SBAs）、音訊/視訊會議伺服器（如果在個別的池中），以及在 [網路設定] 設定中設定了轉送伺服器的子網或 IP 位址。

</div>

<span> </span>

</div>

</div>

</div>

