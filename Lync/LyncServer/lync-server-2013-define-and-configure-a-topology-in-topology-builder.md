---
title: Lync Server 2013： 定義和設定拓撲產生器中的拓撲
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
ms.openlocfilehash: 34d780cd5843d69bc653cd37662c1d9332dc1fc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="120cb-102">定義和設定拓撲中的 Lync Server 2013 的拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="120cb-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="120cb-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="120cb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="120cb-104">執行拓撲產生器來定義新的拓撲或修改現有拓撲不需要在本機系統管理員或特殊權限的網域群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="120cb-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="120cb-105">拓撲產生器會引導您完成來定義您的拓撲，Enterprise Edition 前端集區或 Standard Edition，根據設定的需求所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="120cb-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="120cb-106">完成並發行拓撲，您可以在伺服器上安裝 Lync Server 2013 之前，您必須使用拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="120cb-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="120cb-107">下列程序包含若要定義新的拓撲所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="120cb-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="120cb-108">若要定義拓撲</span><span class="sxs-lookup"><span data-stu-id="120cb-108">To define a topology</span></span>

1.  <span data-ttu-id="120cb-109">啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。</span><span class="sxs-lookup"><span data-stu-id="120cb-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="120cb-110">在拓撲產生器中，選取**新的拓撲**。</span><span class="sxs-lookup"><span data-stu-id="120cb-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="120cb-111">您會收到提示儲存拓撲的位置和檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="120cb-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="120cb-112">提供的拓樸檔案有意義的名稱，並接受預設副檔名.tbxml。</span><span class="sxs-lookup"><span data-stu-id="120cb-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="120cb-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="120cb-113">Click **OK**.</span></span>

3.  <span data-ttu-id="120cb-114">瀏覽至您想要用來儲存新的拓撲 XML 檔案、 輸入檔案名稱，然後再按一下 [**儲存**位置。</span><span class="sxs-lookup"><span data-stu-id="120cb-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="120cb-115">在 [**定義主要網域**] 頁面中，輸入您的組織的主要 SIP 網域名稱，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="120cb-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="120cb-116">在 [**指定其他支援的網域**] 頁面中，輸入其他網域的名稱，如果有的話，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="120cb-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="120cb-117">在 [**定義第一個網站**] 頁面上，輸入名稱與第一個網站的描述，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="120cb-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="120cb-118">在 [**指定網站詳細資料**] 頁面中，輸入網站的位置資訊，然後按一下 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="120cb-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="120cb-119">在**成功定義新的拓撲**] 頁面上，確定已選取 [**開啟新前端精靈當這個精靈關閉時**] 核取方塊，，然後按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="120cb-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="120cb-120">您已定義並儲存拓撲之後，使用新前端精靈來定義前端集區或 Standard Edition 伺服器，為您的網站。</span><span class="sxs-lookup"><span data-stu-id="120cb-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="120cb-121">如需詳細資訊，請參閱[定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="120cb-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

