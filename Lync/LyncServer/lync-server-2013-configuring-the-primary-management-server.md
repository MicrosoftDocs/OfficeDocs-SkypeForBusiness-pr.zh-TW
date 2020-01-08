---
title: Lync Server 2013：設定主要管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b34c685ef59c6315b9d1a667f0715aa4300a83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="e3ab2-102">在 Lync Server 2013 中設定主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="e3ab2-102">Configuring the primary management server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3ab2-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="e3ab2-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="e3ab2-104">若要充分利用 Microsoft Lync Server 2013 中包含的新健康情況監視功能，系統管理員必須先指定電腦作為您的主要管理伺服器;在該電腦上，您必須安裝 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="e3ab2-105">此外，您必須安裝受支援版本的 SQL Server，才能充當 Operations Manager 後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="e3ab2-106">如果您使用系統中心作業管理器2012，您可以使用下列任一版本的 SQL Server 做為後端資料庫：</span><span class="sxs-lookup"><span data-stu-id="e3ab2-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="e3ab2-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="e3ab2-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="e3ab2-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="e3ab2-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="e3ab2-109">如果您使用的是 System Center Operations Manager 2007 R2，建議您安裝 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="e3ab2-110">您也可以使用 SQL Server 2008 R2 作為 System Center Operations Manager 2007 R2 的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="e3ab2-111">如需有關設定 SQL Server 2008 R2 以搭配 System Center Operations Manager 2007 R2 的詳細資訊，請參閱本檔的附錄1。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="e3ab2-112">當您安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您必須安裝該產品的所有元件，包括：</span><span class="sxs-lookup"><span data-stu-id="e3ab2-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="e3ab2-113">運算元據庫</span><span class="sxs-lookup"><span data-stu-id="e3ab2-113">Operational database</span></span>

  - <span data-ttu-id="e3ab2-114">伺服器</span><span class="sxs-lookup"><span data-stu-id="e3ab2-114">Server</span></span>

  - <span data-ttu-id="e3ab2-115">控制</span><span class="sxs-lookup"><span data-stu-id="e3ab2-115">Console</span></span>

  - <span data-ttu-id="e3ab2-116">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e3ab2-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="e3ab2-117">網頁主控台</span><span class="sxs-lookup"><span data-stu-id="e3ab2-117">Web console</span></span>

  - <span data-ttu-id="e3ab2-118">報告</span><span class="sxs-lookup"><span data-stu-id="e3ab2-118">Reporting</span></span>

  - <span data-ttu-id="e3ab2-119">資料倉儲</span><span class="sxs-lookup"><span data-stu-id="e3ab2-119">Data warehouse</span></span>

<span data-ttu-id="e3ab2-120">這些元件及其安裝將不會在這份檔中詳細討論。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="e3ab2-121">如需 System Center Operations Manager 2007 R2 的詳細資料，請參閱 Operations Manager 2007 R2 <http://go.microsoft.com/fwlink/p/?linkid=257526>檔，以及系統中心作業管理員2012檔<http://go.microsoft.com/fwlink/p/?linkid=257527>。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <http://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="e3ab2-122">如果您要使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1 做為後端資料庫，請遵循這些指示。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="e3ab2-123">如果您使用系統中心作業管理器2012，則可以使用 SQL Server 2012 做為後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="e3ab2-124">如需有關 SQL Server 2012 的詳細資訊，請參閱 SQL Server 2012 [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)的線上圖書。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="e3ab2-125">請記住，每個 Lync Server 部署只能有一個主要管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="e3ab2-126">此外，雖然您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2，但您無法同時執行這兩個應用程式，您必須選擇其中一個。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="e3ab2-127">例如，如果您執行的是 System Center Operations Manager 2012，那麼您所有的 System Center agent 也必須執行 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="e3ab2-128">您不能有一些代理程式正在執行 System Center Operations Manager 2012，以及其他執行 System Center Operations Manager 2007 R2 的代理程式。</span><span class="sxs-lookup"><span data-stu-id="e3ab2-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

