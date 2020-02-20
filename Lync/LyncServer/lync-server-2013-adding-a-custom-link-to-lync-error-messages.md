---
title: Lync Server 2013： 將自訂連結新增到 Lync 錯誤訊息
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
ms.openlocfilehash: 4c02534c76a26313818e9ed4af8c51c31621bbd7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>將自訂連結新增到 Lync Server 2013 中的 Lync 錯誤訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

藉由將連結新增至您自己的疑難排解或 help desk 資訊自訂 Lync 2013 的錯誤訊息。 若要這麼做，請使用**New-csclientpolicy**或**Set-csclientpolicy** CustomLinkInErrorMessages 參數與 Lync Server 管理命令介面指令程式。 自訂連結的文字是 「 按這裡取得支援主題從您的系統管理員 」，而且無法自訂。

例如，下列命令會造成自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區，並將連結的目的地設定為http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

使用**Grant-csclientpolicy**將此新原則指派給使用者。 如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的**New-csclientpolicy**和**Grant-csclientpolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

