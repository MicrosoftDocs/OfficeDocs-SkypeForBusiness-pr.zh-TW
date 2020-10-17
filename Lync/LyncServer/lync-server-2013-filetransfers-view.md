---
title: Lync Server 2013： FileTransfers view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500870"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="727e0-102">Lync Server 2013 中的 FileTransfers 視圖</span><span class="sxs-lookup"><span data-stu-id="727e0-102">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="727e0-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="727e0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="727e0-104">FileTransfer view 會儲存對等檔案傳輸會話的資訊。</span><span class="sxs-lookup"><span data-stu-id="727e0-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="727e0-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="727e0-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="727e0-106">FileTransfers view 包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。</span><span class="sxs-lookup"><span data-stu-id="727e0-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="727e0-107">欄</span><span class="sxs-lookup"><span data-stu-id="727e0-107">Column</span></span></th>
<th><span data-ttu-id="727e0-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="727e0-108">Data Type</span></span></th>
<th><span data-ttu-id="727e0-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="727e0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="727e0-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-111">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="727e0-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="727e0-112">已傳輸的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="727e0-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="727e0-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-114">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="727e0-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="727e0-115">可用來識別與此訊息相關聯的每則後續訊息。</span><span class="sxs-lookup"><span data-stu-id="727e0-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="727e0-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-117">唯一</span><span class="sxs-lookup"><span data-stu-id="727e0-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="727e0-118">唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="727e0-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="727e0-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-120">位</span><span class="sxs-lookup"><span data-stu-id="727e0-120">bit</span></span></p></td>
<td><p><span data-ttu-id="727e0-p102">可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="727e0-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="727e0-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-124">位</span><span class="sxs-lookup"><span data-stu-id="727e0-124">bit</span></span></p></td>
<td><p><span data-ttu-id="727e0-p103">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="727e0-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="727e0-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="727e0-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="727e0-128">位</span><span class="sxs-lookup"><span data-stu-id="727e0-128">bit</span></span></p></td>
<td><p><span data-ttu-id="727e0-p104">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="727e0-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

