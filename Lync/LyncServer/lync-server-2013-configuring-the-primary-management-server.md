---
title: Lync Server 2013：設定主要管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4fee1fa728c3c418c1f837a83248d95df7e7544
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532310"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a><span data-ttu-id="fc222-102">在 Lync Server 2013 中設定主要管理伺服器</span><span class="sxs-lookup"><span data-stu-id="fc222-102">Configuring the primary management server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc222-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="fc222-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="fc222-104">為了充分利用 Microsoft Lync Server 2013 中包含的新狀況監視功能，管理員必須先指定一部電腦做為您的主要管理伺服器;在該電腦上，您必須安裝 System Center Operations Manager 2007 R2 或 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="fc222-104">In order to take full advantage of the new health monitoring capabilities included in Microsoft Lync Server 2013 administrators must first designate a computer to act as your primary management server; on that computer you must then install System Center Operations Manager 2007 R2 or System Center Operations Manager 2012.</span></span> <span data-ttu-id="fc222-105">此外，您必須安裝支援的 SQL Server 版本，以當作 Operations Manager 後端資料庫運作。</span><span class="sxs-lookup"><span data-stu-id="fc222-105">In addition, you must install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span> <span data-ttu-id="fc222-106">如果您使用 System Center Operations Manager 2012，您可以使用下列任何版本的 SQL Server 作為後端資料庫：</span><span class="sxs-lookup"><span data-stu-id="fc222-106">If you are using System Center Operations Manager 2012 you can use any of the following versions of SQL Server as your back-end database:</span></span>

  - <span data-ttu-id="fc222-107">SQL Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="fc222-107">SQL Server 2008 R2 Service Pack 1</span></span>

  - <span data-ttu-id="fc222-108">SQL Server 2008 R2 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="fc222-108">SQL Server 2008 R2 Service Pack 2</span></span>

<span data-ttu-id="fc222-109">如果您使用 System Center Operations Manager 2007 R2，建議您安裝 SQL Server 2005 Service Pack 4 或 SQL Server 2008 Service Pack 3。</span><span class="sxs-lookup"><span data-stu-id="fc222-109">If you are using System Center Operations Manager 2007 R2 it is recommended that you install either SQL Server 2005 Service Pack 4 or SQL Server 2008 Service Pack 3.</span></span> <span data-ttu-id="fc222-110">您也可以使用 SQL Server 2008 R2 作為 System Center Operations Manager 2007 R2 的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="fc222-110">You can also use SQL Server 2008 R2 as the backend database for System Center Operations Manager 2007 R2.</span></span> <span data-ttu-id="fc222-111">如需設定 SQL Server 2008 R2 以搭配 System Center Operations Manager 2007 R2 的詳細資訊，請參閱本檔的附錄1。</span><span class="sxs-lookup"><span data-stu-id="fc222-111">See Appendix 1 of this documentation for more information on configuring SQL Server 2008 R2 to work with System Center Operations Manager 2007 R2.</span></span>

<span data-ttu-id="fc222-112">當您安裝 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您需要安裝該產品的所有元件，包括：</span><span class="sxs-lookup"><span data-stu-id="fc222-112">When you install System Center Operations Manager 2012 or System Center Operations Manager 2007 R2 you need to install all the components of that product, including:</span></span>

  - <span data-ttu-id="fc222-113">操作資料庫</span><span class="sxs-lookup"><span data-stu-id="fc222-113">Operational database</span></span>

  - <span data-ttu-id="fc222-114">伺服器</span><span class="sxs-lookup"><span data-stu-id="fc222-114">Server</span></span>

  - <span data-ttu-id="fc222-115">安慰</span><span class="sxs-lookup"><span data-stu-id="fc222-115">Console</span></span>

  - <span data-ttu-id="fc222-116">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fc222-116">Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="fc222-117">Web 主控台</span><span class="sxs-lookup"><span data-stu-id="fc222-117">Web console</span></span>

  - <span data-ttu-id="fc222-118">Reporting</span><span class="sxs-lookup"><span data-stu-id="fc222-118">Reporting</span></span>

  - <span data-ttu-id="fc222-119">資料倉儲</span><span class="sxs-lookup"><span data-stu-id="fc222-119">Data warehouse</span></span>

<span data-ttu-id="fc222-120">本文件中不會詳細說明這些元件和其安裝。</span><span class="sxs-lookup"><span data-stu-id="fc222-120">These components and their installation will not be discussed in detail in this document.</span></span> <span data-ttu-id="fc222-121">如需 System Center Operations Manager 2007 R2 的詳細資訊，請參閱 Operations Manager 2007 R2 檔 <https://go.microsoft.com/fwlink/p/?linkid=257526> ，以及 System Center Operations manager 2012 檔，網址為 <https://go.microsoft.com/fwlink/p/?linkid=257527> 。</span><span class="sxs-lookup"><span data-stu-id="fc222-121">For details about System Center Operations Manager 2007 R2, see the Operations Manager 2007 R2 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257526> and the System Center Operations Manager 2012 documentation at <https://go.microsoft.com/fwlink/p/?linkid=257527>.</span></span> <span data-ttu-id="fc222-122">如果您要使用 SQL Server 2005 或 SQL Server 2008 Service Pack 1 作為後端資料庫，則應該遵循這些指示。</span><span class="sxs-lookup"><span data-stu-id="fc222-122">You should follow those instructions if you are going to use SQL Server 2005 or SQL Server 2008 Service Pack 1 as your back-end database.</span></span>

<span data-ttu-id="fc222-123">如果您使用 System Center Operations Manager 2012，您可以使用 SQL Server 2012 作為後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="fc222-123">If you are using System Center Operations Manager 2012 then you can use SQL Server 2012 as your back-end database.</span></span> <span data-ttu-id="fc222-124">如需 SQL Server 2012 的詳細資訊，請參閱線上叢書 for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) 。</span><span class="sxs-lookup"><span data-stu-id="fc222-124">For details about SQL Server 2012, see Books Online for SQL Server 2012 at [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528).</span></span>

<span data-ttu-id="fc222-125">請記住，每個 Lync Server 部署只能有一個主要管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="fc222-125">Keep in mind that you can only have a single Primary Management Server per Lync Server deployment.</span></span> <span data-ttu-id="fc222-126">此外，當您可以使用 System Center Operations Manager 2012 或 System Center Operations Manager 2007 R2 時，您無法同時執行這兩個應用程式，您必須選擇其中一個。</span><span class="sxs-lookup"><span data-stu-id="fc222-126">Also, while you can use either System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, you cannot run the two applications simultaneously—you must choose one or the other.</span></span> <span data-ttu-id="fc222-127">例如，如果您正在執行 System Center Operations Manager 2012，則所有 System Center agent 也必須執行 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="fc222-127">For example, if you are running System Center Operations Manager 2012 then all your System Center agents must also be running System Center Operations Manager 2012.</span></span> <span data-ttu-id="fc222-128">您無法讓部分代理程式執行 System Center Operations Manager 2012 及其他執行 System Center Operations Manager 2007 R2 的代理程式。</span><span class="sxs-lookup"><span data-stu-id="fc222-128">You cannot have some agents running System Center Operations Manager 2012 and other agents running System Center Operations Manager 2007 R2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

