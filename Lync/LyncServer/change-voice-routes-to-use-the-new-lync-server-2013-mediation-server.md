---
title: 變更語音路由以使用新的 Lync Server 2013 轉送伺服器
description: 變更語音路由以使用新的 Lync Server 2013 轉送伺服器。
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
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545739"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="56c94-103">變更語音路由以使用新的 Lync Server 2013 轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="56c94-103">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56c94-104">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="56c94-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="56c94-105">此程式會變更語音路由以使用 Lync Server 2013 轉送伺服器，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="56c94-105">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="56c94-106">變更語音路由以使用新的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="56c94-106">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="56c94-107">Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="56c94-107">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="56c94-108">在左窗格中，選取 [ **語音路由** ]，然後選取 [ **路由**]。</span><span class="sxs-lookup"><span data-stu-id="56c94-108">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="56c94-109">按一下 [新增]\*\*\*\*，以建立新的語音路由。</span><span class="sxs-lookup"><span data-stu-id="56c94-109">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="56c94-110">填寫下列欄位：</span><span class="sxs-lookup"><span data-stu-id="56c94-110">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="56c94-111">**名稱**：輸入語音路由的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="56c94-111">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="56c94-112">若為此檔，我們會使用 **W15PSTNRoute**。</span><span class="sxs-lookup"><span data-stu-id="56c94-112">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="56c94-113">**描述**：輸入語音路由的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="56c94-113">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="56c94-114">略過後續的所有區段，直到 [關聯的閘道]\*\*\*\* 出現為止。</span><span class="sxs-lookup"><span data-stu-id="56c94-114">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="56c94-115">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="56c94-115">Click **Add**.</span></span> <span data-ttu-id="56c94-116">選取新的預設閘道，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="56c94-116">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="56c94-117">在 [關聯的 PSTN 使用方式]\*\*\*\* 底下，按一下 [選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56c94-117">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="56c94-118">從 [ **選取 PSTN 使用方式記錄** ] 頁面中，選取記錄名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="56c94-118">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="56c94-119">在 [新增語音路由]\*\*\*\* 頁面中，按一下 [確定]\*\*\*\*，以建立**語音路由**。</span><span class="sxs-lookup"><span data-stu-id="56c94-119">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="56c94-120">在 [語音路由]\*\*\*\* 頁面中，選取 [路由]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="56c94-120">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="56c94-121">將新建立的路由移至清單的頂端，然後選取 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="56c94-121">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

