---
title: Lync Server 2013： FileTransfers view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="3bc9b-102">Lync Server 2013 中的 [FileTransfers] 視圖</span><span class="sxs-lookup"><span data-stu-id="3bc9b-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bc9b-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3bc9b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3bc9b-104">FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="3bc9b-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3bc9b-106">[FileTransfers] 視圖會包含 [ <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013</A> ] 的 [SessionDetails] 視圖中的所有資料行，以及下列所列的欄。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3bc9b-107">左欄</span><span class="sxs-lookup"><span data-stu-id="3bc9b-107">Column</span></span></th>
<th><span data-ttu-id="3bc9b-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="3bc9b-108">Data Type</span></span></th>
<th><span data-ttu-id="3bc9b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3bc9b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3bc9b-110"><strong>副檔名</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-111">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="3bc9b-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-112">已傳輸檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc9b-113"><strong>C</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-114">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="3bc9b-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-115">用來識別與此郵件相關聯的每一封後續訊息。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bc9b-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="3bc9b-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-118">唯一識別碼，區分涉及相同檔案名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc9b-119"><strong>接受</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-120">稍微</span><span class="sxs-lookup"><span data-stu-id="3bc9b-120">bit</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-121">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="3bc9b-122">如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3bc9b-123"><strong>否決</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-124">稍微</span><span class="sxs-lookup"><span data-stu-id="3bc9b-124">bit</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-125">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="3bc9b-126">如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3bc9b-127"><strong>取消</strong></span><span class="sxs-lookup"><span data-stu-id="3bc9b-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="3bc9b-128">稍微</span><span class="sxs-lookup"><span data-stu-id="3bc9b-128">bit</span></span></p></td>
<td><p><span data-ttu-id="3bc9b-129">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="3bc9b-130">如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</span><span class="sxs-lookup"><span data-stu-id="3bc9b-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

