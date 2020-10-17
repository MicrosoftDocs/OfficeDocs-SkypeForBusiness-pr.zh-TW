---
title: Lync Server 2013： SQL Server 的系統需求
description: Lync Server 2013： SQL Server 的系統需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524136174be8798aed1dc7d5d236dbb45ab18330
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562629"
---
# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="17378-103">Lync Server 2013 中 SQL Server 的系統需求</span><span class="sxs-lookup"><span data-stu-id="17378-103">System requirements for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17378-104">_**主題上次修改日期：** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="17378-104">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="17378-105">在您部署 Enterprise Edition server 之前，請在符合硬體需求的專用電腦上安裝 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="17378-105">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="17378-106">如需硬體需求的詳細資訊，請參閱支援檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="17378-106">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="17378-107">如需軟體需求的詳細資訊，請參閱支援檔中的 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="17378-107">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="17378-108">如需部署所需許可權的相關資訊，請參閱 [Lync server 2013 中的 SQL Server 部署許可權](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="17378-108">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="17378-109">在建立前端集區之前，您也必須將 Windows 防火牆設定為使用 SQL Server Configuration Manager 來定義伺服器的埠，並在具有高級安全性的 Windows 防火牆中開啟埠，以允許 Lync Server 2013 對 SQL Server 的存取。</span><span class="sxs-lookup"><span data-stu-id="17378-109">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

