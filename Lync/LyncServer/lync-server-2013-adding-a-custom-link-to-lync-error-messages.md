---
title: Lync Server 2013：新增自訂連結到 Lync 錯誤訊息
description: Lync Server 2013：新增自訂連結到 Lync 錯誤訊息。
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
ms.openlocfilehash: a5d333b6f27e10e5092de23fcdf1d37fd75e75a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560029"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="2bacc-103">在 Lync Server 2013 中新增自訂連結到 Lync 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="2bacc-103">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bacc-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2bacc-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2bacc-105">新增您自己的疑難排解或問訊台資訊的連結，以自訂 Lync 2013 錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="2bacc-105">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="2bacc-106">若要這麼做，請使用**New-CSClientPolicy**或**Set-CSClientPolicy**   Lync Server 管理命令介面 Cmdlet 搭配 CustomLinkInErrorMessages 參數。</span><span class="sxs-lookup"><span data-stu-id="2bacc-106">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="2bacc-107">自訂連結的文字是「按一下您系統管理員的支援主題」，而且無法進行自訂。</span><span class="sxs-lookup"><span data-stu-id="2bacc-107">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="2bacc-108">例如，下列命令會使自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區域中，並將連結目的地設定為 http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="2bacc-108">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="2bacc-109">使用 **Grant-CSClientPolicy** 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="2bacc-109">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="2bacc-110">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 **New-CSClientPolicy** 和 **Grant-CSClientPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="2bacc-110">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

