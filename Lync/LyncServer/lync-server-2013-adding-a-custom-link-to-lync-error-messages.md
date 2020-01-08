---
title: Lync Server 2013：新增自訂連結到 Lync 錯誤訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f62dd7841f77a519653a658131423a89f77ed012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="3e5ae-102">在 Lync Server 2013 中新增自訂連結到 Lync 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="3e5ae-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e5ae-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3e5ae-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3e5ae-104">透過新增您自己的疑難排解或技術支援資訊的連結，來自訂 Lync 2013 錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="3e5ae-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="3e5ae-105">若要這樣做，請使用**CSClientPolicy**或**CSClientPolicy** 的 Lync Server Management Shell Cmdlet 搭配 CustomLinkInErrorMessages 參數。</span><span class="sxs-lookup"><span data-stu-id="3e5ae-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="3e5ae-106">自訂連結的文字為「按一下這裡以取得管理員支援主題」，且無法進行自訂。</span><span class="sxs-lookup"><span data-stu-id="3e5ae-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="3e5ae-107">例如，下列命令會使自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區域，並將連結目的地設定為http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="3e5ae-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="3e5ae-108">使用**授與 CSClientPolicy**將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="3e5ae-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="3e5ae-109">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的**新 CSClientPolicy**與**授與 CSClientPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="3e5ae-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

