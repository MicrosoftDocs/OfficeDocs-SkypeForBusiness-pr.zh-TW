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
ms.openlocfilehash: aa65580cd9138b58792d4a0f0621bfe6f5f10c9c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a><span data-ttu-id="3841e-102">將自訂連結新增到 Lync Server 2013 中的 Lync 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="3841e-102">Adding a custom link to Lync error messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3841e-103">_**上次修改主題：** 2013年-02-20 個_</span><span class="sxs-lookup"><span data-stu-id="3841e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3841e-104">藉由將連結新增至您自己的疑難排解或 help desk 資訊自訂 Lync 2013 的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="3841e-104">Customize Lync 2013 error messages by adding a link to your own troubleshooting or help desk information.</span></span> <span data-ttu-id="3841e-105">若要這麼做，請使用**New-csclientpolicy**或**Set-csclientpolicy** CustomLinkInErrorMessages 參數與 Lync Server 管理命令介面指令程式。</span><span class="sxs-lookup"><span data-stu-id="3841e-105">To do this, use the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the CustomLinkInErrorMessages parameter.</span></span> <span data-ttu-id="3841e-106">自訂連結的文字是 「 按這裡取得支援主題從您的系統管理員 」，而且無法自訂。</span><span class="sxs-lookup"><span data-stu-id="3841e-106">The text of the custom link is "Click here for support topics from your administrator," and it cannot be customized.</span></span>

<span data-ttu-id="3841e-107">例如，下列命令會造成自訂連結出現在每個 Lync 2013 錯誤訊息的註腳區，並將連結的目的地設定為http://contoso.com/help/LyncHelpDesk.aspx:</span><span class="sxs-lookup"><span data-stu-id="3841e-107">For example, the following command causes the custom link to appear in the footnote area of every Lync 2013 error message and sets the link destination to http://contoso.com/help/LyncHelpDesk.aspx:</span></span>

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

<span data-ttu-id="3841e-108">使用**Grant-csclientpolicy**將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="3841e-108">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="3841e-109">如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的**New-csclientpolicy**和**Grant-csclientpolicy** 。</span><span class="sxs-lookup"><span data-stu-id="3841e-109">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

