---
title: Lync Server 2013：備份檔案存放區
description: Lync Server 2013：備份檔案存放區。
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
ms.openlocfilehash: ba6a92d189c39242be1b2167ffc336d9eb406719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563279"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="969bb-103">在 Lync Server 2013 中備份檔案存放區</span><span class="sxs-lookup"><span data-stu-id="969bb-103">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="969bb-104">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="969bb-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="969bb-105">備份 Lync Server 檔存放區時，會包含 Lync Server 元件所使用的所有檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="969bb-105">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="969bb-106">若要備份檔案存放區</span><span class="sxs-lookup"><span data-stu-id="969bb-106">To back up File Stores</span></span>

1.  <span data-ttu-id="969bb-107">若要尋找 Lync Server 檔案存放區的特定位置，請開啟拓撲產生器，然後在 [檔案存放 **區** ] 節點中查看。</span><span class="sxs-lookup"><span data-stu-id="969bb-107">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="969bb-108">使用 Robocopy 或其他檔案系統管理工具，將每個檔案存放區複製到 $Backup 儲存區 \\ 。</span><span class="sxs-lookup"><span data-stu-id="969bb-108">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

