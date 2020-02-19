---
title: 變更語音路由以使用新的 Lync Server 2013 中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 386789c5cb3753db2df8910a1fde437a33849ca7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="cd962-102">變更語音路由以使用新的 Lync Server 2013 中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="cd962-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd962-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="cd962-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cd962-104">此程序會變更語音路由以使用 Lync Server 2013 中繼伺服器，而不是舊版 Office Communications Server 2007 R2 中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="cd962-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="cd962-105">變更語音路由以使用新的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="cd962-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="cd962-106">Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="cd962-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="cd962-107">在左窗格中，選取 [**語音路由]** ，然後**路由**]。</span><span class="sxs-lookup"><span data-stu-id="cd962-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="cd962-108">按一下 [新增]\*\*\*\*，以建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="cd962-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="cd962-109">填寫下列欄位：</span><span class="sxs-lookup"><span data-stu-id="cd962-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="cd962-110">**名稱**：輸入語音路由的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="cd962-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="cd962-111">這份文件中，我們將使用**W15PSTNRoute**。</span><span class="sxs-lookup"><span data-stu-id="cd962-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="cd962-112">**描述**：輸入語音路由的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="cd962-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="cd962-113">略過後續的所有區段，直到 [關聯的閘道]\*\*\*\* 出現為止。</span><span class="sxs-lookup"><span data-stu-id="cd962-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="cd962-114">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cd962-114">Click **Add**.</span></span> <span data-ttu-id="cd962-115">選取新的預設閘道，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="cd962-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="cd962-116">在 [關聯的 PSTN 使用方式]\*\*\*\* 底下，按一下 [選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd962-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="cd962-117">從 [**選取 PSTN 使用方式記錄**] 頁面上，選取記錄名稱，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="cd962-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="cd962-118">在 [新增語音路由]\*\*\*\* 頁面中，按一下 [確定]\*\*\*\*，以建立**語音路由**。</span><span class="sxs-lookup"><span data-stu-id="cd962-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="cd962-119">在 [語音路由]\*\*\*\* 頁面中，選取 [路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd962-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="cd962-120">將新建的路由移至清單頂端，然後選取 [**認可]**。</span><span class="sxs-lookup"><span data-stu-id="cd962-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

