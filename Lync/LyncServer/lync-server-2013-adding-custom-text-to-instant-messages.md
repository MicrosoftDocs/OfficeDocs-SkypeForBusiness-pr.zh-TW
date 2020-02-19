---
title: Lync Server 2013： 將自訂文字新增至立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ebaaaa693248cd11ebcb663692fa2805cdce20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>將自訂文字新增至 Lync Server 2013 中的立即訊息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

立即訊息 (IM) 交談藉由使用**New-csclientpolicy**或**Set-csclientpolicy** Lync Server 管理命令介面 cmdlet 搭配 IMWarning 參數每個 Lync 2013 的開頭新增免責聲明或警告。

在下列範例中的命令會將安全性提醒新增頂端的 [交談] 視窗中，每當新的 IM 交談開始：

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

使用**Grant-csclientpolicy**將此新原則指派給使用者。 如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的**New-csclientpolicy**和**Grant-csclientpolicy** 。

</div>

<span> </span>

</div>

</div>

</div>

