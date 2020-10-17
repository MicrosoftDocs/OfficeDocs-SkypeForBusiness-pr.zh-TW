---
title: Lync Server 2013：在拓撲產生器中定義及設定拓撲
description: Lync Server 2013：在拓撲產生器中定義及設定拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a1f29ec78cf7cfd3856d3f1aa87a22dc0bbe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569939"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="9ff16-103">在 Lync Server 2013 的拓撲產生器中定義及設定拓撲</span><span class="sxs-lookup"><span data-stu-id="9ff16-103">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ff16-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9ff16-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9ff16-105">執行拓撲產生器以定義新的拓撲或修改現有的拓撲，不需要本機系統管理員或特權網域群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="9ff16-105">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="9ff16-106">拓撲產生器會引導您逐步完成定義 Enterprise Edition 前端集區或 Standard Edition 的拓撲所需的步驟，視您的設定需求而定。</span><span class="sxs-lookup"><span data-stu-id="9ff16-106">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="9ff16-107">您必須先使用拓撲產生器，才可在伺服器上安裝 Lync Server 2013，以完成併發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="9ff16-107">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="9ff16-108">下列套裝程式含定義新拓撲所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="9ff16-108">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="9ff16-109">若要定義拓撲</span><span class="sxs-lookup"><span data-stu-id="9ff16-109">To define a topology</span></span>

1.  <span data-ttu-id="9ff16-110">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="9ff16-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9ff16-111">在 [拓撲產生器] 中，選取 [ **新增拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="9ff16-111">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="9ff16-112">系統會提示您輸入儲存拓撲的位置和檔案名。</span><span class="sxs-lookup"><span data-stu-id="9ff16-112">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="9ff16-113">為拓撲檔案提供有意義的名稱，並接受 redmond.tbxml 的預設副檔名。</span><span class="sxs-lookup"><span data-stu-id="9ff16-113">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="9ff16-114">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ff16-114">Click **OK**.</span></span>

3.  <span data-ttu-id="9ff16-115">流覽至您要儲存新拓撲 XML 檔案的位置，輸入檔案名，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9ff16-115">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="9ff16-116">在 [ **定義主域** ] 頁面上，輸入組織之主要 SIP 網域的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9ff16-116">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="9ff16-117">在 [ **指定其他支援的網域** ] 頁面上，輸入其他網域的名稱（如果有的話），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9ff16-117">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="9ff16-118">在 [ **定義第一個網站** ] 頁面上，輸入第一個網站的名稱和描述，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9ff16-118">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="9ff16-119">在 [ **指定網站詳細資料** ] 頁面上，輸入網站的位置資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9ff16-119">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="9ff16-120">在 [已 **成功定義新拓撲** ] 頁面上，確定已選取 [在 **此嚮導關閉時開啟新的前端嚮導]** 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="9ff16-120">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="9ff16-121">在您定義及儲存拓撲之後，請使用新的前端嚮導為網站定義前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="9ff16-121">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="9ff16-122">如需詳細資訊，請參閱 [在 Lync server 2013 中定義及設定前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9ff16-122">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

