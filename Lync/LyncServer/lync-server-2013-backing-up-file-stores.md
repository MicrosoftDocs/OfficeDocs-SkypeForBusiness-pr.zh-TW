---
title: Lync Server 2013： 備份檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e61c9a70477d18ebdacaf9233bbbb0693bb74a2e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="29901-102">備份 Lync Server 2013 中的檔案存放區</span><span class="sxs-lookup"><span data-stu-id="29901-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29901-103">_**上次修改主題：** 2013年-02-17_</span><span class="sxs-lookup"><span data-stu-id="29901-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="29901-104">備份 Lync Server 檔案存放區包含的所有檔案和 Lync Server 元件所使用的資料夾。</span><span class="sxs-lookup"><span data-stu-id="29901-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="29901-105">若要備份檔案存放區</span><span class="sxs-lookup"><span data-stu-id="29901-105">To back up File Stores</span></span>

1.  <span data-ttu-id="29901-106">若要找出您 Lync 伺服器檔案存放區的特定位置，請開啟拓撲產生器，並查看**檔案會儲存**] 節點。</span><span class="sxs-lookup"><span data-stu-id="29901-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="29901-107">使用 Robocopy 或其他檔案系統管理工具，將每個檔案存放區複製到 $Backup\\檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="29901-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

