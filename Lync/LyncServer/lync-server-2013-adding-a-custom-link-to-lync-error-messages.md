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
ms.openlocfilehash: 619bdaaa1a1c3b7723f2df9c74e106321bdb054c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521450"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>在 Lync Server 2013 中新增自訂連結到 Lync 錯誤訊息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

新增您自己的疑難排解或問訊台資訊的連結，以自訂 Lync 2013 錯誤訊息。 若要這麼做，請使用**New-CSClientPolicy**或**Set-CSClientPolicy**   Lync Server 管理命令介面 Cmdlet 搭配 CustomLinkInErrorMessages 參數。 自訂連結的文字是「按一下您系統管理員的支援主題」，而且無法進行自訂。

例如，下列命令會使自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區域中，並將連結目的地設定為 http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用 **Grant-CSClientPolicy** 將此新原則指派給使用者。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

