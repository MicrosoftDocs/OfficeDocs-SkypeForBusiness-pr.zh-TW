---
title: 通話駐留的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb507ddf7fc47714781e83da0fa77d093f193c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

Lync Server 2013 通話駐留應用程式可讓 Enterprise Voice 使用者執行下列其中一項動作：

  - 將呼叫放入保留，然後從相同電話或其他電話擷取通話。

  - 將呼叫放入保留，並將它轉接至某個部門或一般區域 (例如，能夠銷售部門或是倉儲是公共區域電話)。

  - 放入保留的通話，並保留原始的自動答錄服務電話空出來處理通話。

當使用者公園通話，Lync Server 將傳輸的暫存的數字，稱為*軌道*，通話保留並在擷取或逾時之前呼叫。Lync Server 會將軌道傳送給駐留通話的使用者。 若要擷取駐留的通話，使用者可以撥打軌道號碼，或按一下軌道連結] 或 [交談] 視窗中的按鈕。

駐留通話的使用者可以通知有人能夠軌道號碼給其他人使用外部的機制，例如立即訊息 (IM) 或分頁系統，來擷取通話。 駐留通話的使用者可以將保留的交談視窗開啟擷取通話時收到通知。

因為軌道範圍是全域唯一的就可以從任何 Lync Server 網站或 PBX 電話擷取通話，如果路由已適當設定。 如果沒有人在可設定的時間內擷取通話，電話鈴響會回到駐留的人員。 如果該人員未接聽回電時，來電會被轉接至後援目的地，例如運算子，如果有設定。 您可以設定的前一到十個一定時間轉接電話鈴響備份的次數。 如果沒有人接聽的轉接的來電，通話會中斷。 擷取或中斷連線的來電時，會釋出軌道。

當您部署通話駐留時，您需要為駐留通話保留範圍的分機號碼。 這些副檔名必須是虛擬分機： 沒有任何使用者或電話指派給他們的分機。 您接著使用的分機號碼的範圍設定通話駐留軌道表，並指定哪些應用程式服務主控處理每個範圍的通話駐留應用程式。 每個前端集區上對應後端伺服器用來管理通話駐留的集區具有通話駐留列表。 軌道範圍的清單是否儲存在中央管理存放區，而且會用來將軌道路由傳送至目的地集區。 通話駐留應用程式已在其中部署及設定每個 Lync 伺服器集區可以有一或多個軌道範圍。 在 Lync Server 部署，軌道範圍必須是全域唯一的。

您也可以設定其他通話駐留設定，例如其中來電會被重新導向若使用者逾時間，以及是否在電話上的人所聽到駐留時的等候音樂。 您也可以指定要播放在通話時的等候音樂檔保留。

<div>


> [!NOTE]  
> 通話駐留的自訂等候音樂上保留檔案不會備份 Lync Server 2013 災害復原程序的一部分，而且如果損毀、 損毀，或清除上傳至集區的檔案將會遺失。 永遠保持個別檔案的備份自訂等候音樂上保留已上傳的通話駐留。



</div>

通話駐留應用程式是企業語音元件。 當您部署企業語音時，將通話駐留應用程式已安裝，並自動啟動。 您可以使用通話駐留之前，不過，Enterprise Voice 系統管理員必須將其設定並啟用的使用者透過語音原則。

</div>

<span> </span>

</div>

</div>

</div>

