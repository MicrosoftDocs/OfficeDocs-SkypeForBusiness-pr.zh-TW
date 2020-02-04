---
title: Lync Server 2013：新增自訂連結到 Lync 錯誤訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63523013d8df74a52fee307192d3f60eb5232121
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>在 Lync Server 2013 中新增自訂連結到 Lync 錯誤訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

透過新增您自己的疑難排解或技術支援資訊的連結，來自訂 Lync 2013 錯誤訊息。 若要這樣做，請使用**CSClientPolicy**或**CSClientPolicy** 的 Lync Server Management Shell Cmdlet 搭配 CustomLinkInErrorMessages 參數。 自訂連結的文字為「按一下這裡以取得管理員支援主題」，且無法進行自訂。

例如，下列命令會使自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區域，並將連結目的地設定為http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用**授與 CSClientPolicy**將此新原則指派給使用者。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的**新 CSClientPolicy**與**授與 CSClientPolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

