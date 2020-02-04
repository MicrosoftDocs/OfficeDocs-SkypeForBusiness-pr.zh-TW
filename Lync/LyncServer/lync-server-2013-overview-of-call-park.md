---
title: Lync Server 2013：通話寄存的概覽
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
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話寄存的概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Lync Server 2013 通話寄存應用程式可讓企業語音使用者執行下列任何一項操作：

  - 保留通話，然後從同一個電話或另一個電話取回通話。

  - [保留通話] 可將來電轉接到部門或一般區域（例如，移至 [銷售部門] 或 [有共同區域電話的倉庫]）。

  - 保留通話，並保留原始的應答電話供其他通話。

當使用者公園來電時，Lync Server 會將來電轉接到暫時號碼（稱為*軌道*），通話會一直留在進行檢索或超時。Lync Server 會將軌道傳送給停用通話的使用者。 若要取得寄存通話，使用者可以撥打軌道編號，或按一下交談視窗中的 [軌道] 連結或按鈕。

停用通話的使用者可以使用外部機制（例如立即訊息（IM）或分頁系統），通知某人使用外部機制來取得通話，以將軌道編號傳達給其他人。 停用通話的使用者可以讓交談視窗保持開啟，在檢索通話時接收通知。

由於軌道範圍是全域唯一的，因此，如果路由設定正確，就可以從任何 Lync Server 網站或 PBX 手機中檢索來電。 如果沒有人在可設定的時間內檢索呼叫，來電會傳回寄存該通話的人。 如果該人員不接聽 ringback，則會將來電轉接到回退目的地，例如，如果已設定，就會傳送給接線員。 您可以將呼叫響鈴的次數設定為從1到十次轉接。 如果沒有人接聽轉接來電，通話就會中斷連線。 檢索或斷開通話時，會釋放軌道。

當您部署 [通話寄存] 時，您必須為 [停止通話] 保留延伸號碼的範圍。 這些延伸必須是虛擬延伸：沒有指派使用者或電話的延伸。 接著，您可以將 [通話駐留軌道] 表格設定為延伸的範圍，並指定哪個應用程式服務主持處理每個範圍的通話駐留應用程式。 每個前端池在對應的後端伺服器上都有一個 [呼叫駐留] 資料表，用來管理停在該池中的呼叫。 軌道範圍清單會儲存在中央管理存放區中，並用於將軌道式路由到目的地池。 已部署並設定通話駐留應用程式的每個 Lync 伺服器池都可以有一個或多個軌道範圍。 在 Lync Server 部署中，軌道範圍必須全域唯一。

您也可以設定其他通話寄存設定，例如，如果電話被重新導向，以及手機上的人員是否會聽到音樂，請在停用時撥打。 您也可以指定在通話保留期間播放音樂檔案。

<div>


> [!NOTE]  
> 在 Lync Server 2013 災害復原程式中，如果您已將檔案上傳的檔案遭到損毀、損毀或刪除，將會遺失 [通話駐留] 的自訂音樂保留檔案，而不會將其備份。 針對通話駐留，請務必針對您上傳的自訂音樂保留檔案保留一個單獨的備份複本。



</div>

通話駐留應用程式是企業語音的元件。 當您部署企業語音時，通話寄存應用程式會自動安裝並啟用。 不過，在您可以使用電話寄存前，企業語音管理員必須設定它，並透過語音原則為使用者啟用它。

</div>

<span> </span>

</div>

</div>

</div>

