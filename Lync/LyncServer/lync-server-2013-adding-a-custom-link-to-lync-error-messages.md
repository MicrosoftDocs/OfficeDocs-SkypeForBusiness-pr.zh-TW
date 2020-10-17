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
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="bc4f7-102">在 Lync Server 2013 中新增自訂連結到 Lync 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="bc4f7-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc4f7-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bc4f7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bc4f7-104">新增您自己的疑難排解或問訊台資訊的連結，以自訂 Lync 2013 錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="bc4f7-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="bc4f7-105">若要這麼做，請使用**New-CSClientPolicy**或**Set-CSClientPolicy**   Lync Server 管理命令介面 Cmdlet 搭配 CustomLinkInErrorMessages 參數。</span><span class="sxs-lookup"><span data-stu-id="bc4f7-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="bc4f7-106">自訂連結的文字是「按一下您系統管理員的支援主題」，而且無法進行自訂。</span><span class="sxs-lookup"><span data-stu-id="bc4f7-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="bc4f7-107">例如，下列命令會使自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區域中，並將連結目的地設定為 http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="bc4f7-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="bc4f7-108">使用 **Grant-CSClientPolicy** 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="bc4f7-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="bc4f7-109">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="bc4f7-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

