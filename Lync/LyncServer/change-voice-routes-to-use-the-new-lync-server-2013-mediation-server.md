---
title: 變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器
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
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="4ed13-102">變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器</span><span class="sxs-lookup"><span data-stu-id="4ed13-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ed13-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4ed13-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4ed13-104">這個程式會將語音路由變更為使用 Lync Server 2013 轉送伺服器，而不是舊版 Office 通訊伺服器 2007 R2 轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4ed13-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="4ed13-105">若要變更語音路由以使用新的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4ed13-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="4ed13-106">Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="4ed13-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="4ed13-107">在左窗格中，選取 [**語音路由**]，然後選取 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="4ed13-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="4ed13-108">按一下 [**新增**]，建立新的語音路線。</span><span class="sxs-lookup"><span data-stu-id="4ed13-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="4ed13-109">填寫下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="4ed13-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="4ed13-110">**Name （名稱**）：輸入語音路線的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="4ed13-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="4ed13-111">我們將在這份檔中使用**W15PSTNRoute**。</span><span class="sxs-lookup"><span data-stu-id="4ed13-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="4ed13-112">**描述**：輸入語音路線的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="4ed13-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="4ed13-113">略過其餘所有章節，直到您到達**關聯的閘道**為止。</span><span class="sxs-lookup"><span data-stu-id="4ed13-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="4ed13-114">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4ed13-114">Click **Add**.</span></span> <span data-ttu-id="4ed13-115">選取新的預設閘道，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ed13-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="4ed13-116">在 [**關聯的 PSTN 使用**] 底下，按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="4ed13-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="4ed13-117">從 [**選取 PSTN 使用量記錄**] 頁面，選取記錄名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ed13-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="4ed13-118">從 [**新增語音路由**] 頁面，按一下 **[確定]** 來建立**語音路線**。</span><span class="sxs-lookup"><span data-stu-id="4ed13-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="4ed13-119">從 [**語音路由**] 頁面，選取 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="4ed13-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="4ed13-120">將新建立的路由移到清單頂端，然後選取 [Commit] （**提交**）。</span><span class="sxs-lookup"><span data-stu-id="4ed13-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

