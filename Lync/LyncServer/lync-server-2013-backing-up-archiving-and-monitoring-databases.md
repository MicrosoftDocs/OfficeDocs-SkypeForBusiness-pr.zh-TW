---
title: Lync Server 2013：備份封存和監控資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4f76c0bea6c9ffd98ec0ce6105698dfd3718e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="4a081-102">在 Lync Server 2013 中備份封存與監控資料庫</span><span class="sxs-lookup"><span data-stu-id="4a081-102">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a081-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4a081-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4a081-104">如果您已部署封存或監控，您必須根據組織的 SQL Server 備份原則備份這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="4a081-104">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a081-105">當您備份中央管理存放區時，即會備份封存和監控的設定。</span><span class="sxs-lookup"><span data-stu-id="4a081-105">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="4a081-106">如需詳細資訊，請參閱<A href="lync-server-2013-backing-up-core-data-and-settings.md">在 Lync Server 2013 中備份核心資料和設定</A>。</span><span class="sxs-lookup"><span data-stu-id="4a081-106">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4a081-107">若要進行封存與監控，您可以使用 SQL server 工具（例如 SQL Server Management Studio）執行手動備份，也可以使用 SQL Server 管理工具來排程定期、自動備份。</span><span class="sxs-lookup"><span data-stu-id="4a081-107">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

