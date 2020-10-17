---
title: Lync Server 2013：新增自訂文字到立即訊息
description: Lync Server 2013：新增自訂文字到立即訊息。
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
ms.openlocfilehash: 54f5cf031da0ba4d5bd0b6dbaa7f5ebc9d0b3a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569339"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="ada68-103">在 Lync Server 2013 中新增自訂文字到立即訊息</span><span class="sxs-lookup"><span data-stu-id="ada68-103">Adding custom text to instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ada68-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ada68-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ada68-105">使用 **New-CSClientPolicy** 或 **Set-CSClientPolicy** 具有 IMWarning 參數的 lync Server 管理命令介面 Cmdlet，將免責聲明或警告新增到每個 Lync 2013 立即訊息 (IM) 交談的開頭。</span><span class="sxs-lookup"><span data-stu-id="ada68-105">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="ada68-106">下列範例中的命令會在新的 IM 交談開始時，在交談視窗的頂端加入安全性提醒：</span><span class="sxs-lookup"><span data-stu-id="ada68-106">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="ada68-107">使用 **Grant-CSClientPolicy** 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ada68-107">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="ada68-108">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="ada68-108">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

