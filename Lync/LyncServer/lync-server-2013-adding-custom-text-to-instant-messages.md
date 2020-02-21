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
ms.openlocfilehash: 2e42c04c84d6df91b592bf4709daf36d6822aa49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="64dcf-102">將自訂文字新增至 Lync Server 2013 中的立即訊息</span><span class="sxs-lookup"><span data-stu-id="64dcf-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64dcf-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="64dcf-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="64dcf-104">立即訊息 (IM) 交談藉由使用**New-csclientpolicy**或**Set-csclientpolicy** Lync Server 管理命令介面 cmdlet 搭配 IMWarning 參數每個 Lync 2013 的開頭新增免責聲明或警告。</span><span class="sxs-lookup"><span data-stu-id="64dcf-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="64dcf-105">在下列範例中的命令會將安全性提醒新增頂端的 [交談] 視窗中，每當新的 IM 交談開始：</span><span class="sxs-lookup"><span data-stu-id="64dcf-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="64dcf-106">使用**Grant-csclientpolicy**將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="64dcf-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="64dcf-107">如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的**New-csclientpolicy**和**Grant-csclientpolicy** 。</span><span class="sxs-lookup"><span data-stu-id="64dcf-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

