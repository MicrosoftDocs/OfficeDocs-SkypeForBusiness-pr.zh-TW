---
title: Lync Server 2013：通話駐留的概覽
description: Lync Server 2013：通話駐留的概覽。
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
ms.openlocfilehash: 373a758dcc64dc390255239c0d1fb628308080a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559259"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留概覽

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Lync Server 2013 通話駐留應用程式可讓企業語音使用者執行下列其中一項動作：

  - 進行暫止通話，然後從相同電話或其他電話取得通話。

  - 進行暫止通話，將其轉接至部門或一般區域 (例如，移至銷售部門或存在公共區域電話的倉庫) 。

  - 保留通話，並將原始接聽電話保留空閒狀態供其他電話使用。

當使用者公園通話時，Lync Server 會將來電轉接至暫時號碼（稱為 *軌道*），在此呼叫會保留，直到被取回或超時為止。Lync Server 會將軌道傳送給停用通話的使用者。 若要取得寄存通話，使用者可以撥打軌道號碼，或按一下 [交談] 視窗中的 [軌道] 連結或按鈕。

停用通話的使用者可以使用外部機制（如立即訊息 (IM) 或分頁系統）來通知人員取得通話，以與其他人溝通軌道號碼。 停用通話的使用者可以讓 [交談] 視窗保持開啟，以在檢索來電時收到通知。

因為軌道範圍是全域唯一的，所以如果路由設定正確，可以從任何 Lync Server 網站或 PBX 電話取回來電。 如果沒有人在可設定的時間內取回通話，則呼叫會傳回寄存其的人員。 如果此人沒有回答回電，則會將來電轉接至 fallback 目的地（例如，如果已設定，則為操作員）。 您可以設定來電響鈴的次數，再從一到十次轉接。 如果沒有人接聽轉接的電話，則通話會中斷連線。 檢索或中斷通話呼叫時，會釋放軌道。

當您部署通話駐留時，您必須保留駐留通話的分機號碼範圍。 這些分機必須是虛擬分機：沒有指派使用者或電話的分機號碼。 然後，您可以使用分機號碼範圍設定通話駐留軌道表格，並指定哪些應用程式服務主控處理每個範圍的通話駐留應用程式。 每個前端集區在對應的後端伺服器上都有一個呼叫駐留表，用來管理集區上寄存的呼叫。 軌道範圍的清單儲存在中央管理存放區中，用來將軌道式路由傳送至目的地集區。 在其中部署及設定通話駐留應用程式的每個 Lync 伺服器集區，都可以有一或多個軌道範圍。 軌道範圍在 Lync Server 部署中必須是全域唯一的。

您也可以設定其他通話駐留設定，例如，在通話超時的位置，以及電話上的人員是否會在寄存時，是否會聽到音樂。 您也可以在通話處於保留狀態時，指定要播放的音樂檔案。

<div>


> [!NOTE]  
> 在 Lync Server 2013 嚴重損壞修復程式中，自訂的封存暫止檔案，不會備份通話駐留，如果上傳至集區的檔案損毀、損毀或清除，將會遺失。 請永遠為通話保留，保留您為通話保留所上傳之自訂音樂暫止檔案的個別備份副本。



</div>

通話駐留應用程式是 Enterprise Voice 的元件。 當您部署企業語音時，會自動安裝通話駐留應用程式並加以啟用。 不過，您必須先設定企業語音管理員，並透過語音原則為使用者啟用通話駐留，才可使用通話保留。

</div>

<span> </span>

</div>

</div>

</div>

