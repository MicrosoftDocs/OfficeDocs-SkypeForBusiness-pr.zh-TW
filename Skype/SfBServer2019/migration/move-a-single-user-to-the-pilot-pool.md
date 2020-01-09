---
title: 將單一使用者移至 [試驗] 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將使用者移至您的商務用 skype Server 2019 試用版文件庫。 在下列範例中，在 [註冊機構池] 欄中，pool01.contoso.net 是舊版池，且所有六個使用者都已連線到此池。 使用下列程式將使用者移至商務用 Skype 2019 Server 2019 的 [商務用 Skype] 伺服器的 [控制台] 和 [商務用 Skype 伺服器管理] 命令介面。
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988958"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="ad7e0-105">將單一使用者移至 [試驗] 池</span><span class="sxs-lookup"><span data-stu-id="ad7e0-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="ad7e0-106">您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，從舊版池中將使用者移至您的商務用 skype Server 2019 試用版文件庫。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="ad7e0-107">在下列範例中，在 [**註冊機構池**] 欄中， **pool01.contoso.net**是舊版池，且所有六個使用者都已連線到此池。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="ad7e0-108">使用下列程式將使用者移至商務用 Skype 2019 Server 2019 的 [商務用 Skype] 伺服器的 [控制台] 和 [商務用 Skype 伺服器管理] 命令介面。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="ad7e0-109">使用商務用 Skype Server 2019 [控制台] 移動使用者</span><span class="sxs-lookup"><span data-stu-id="ad7e0-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="ad7e0-110">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="ad7e0-111">開啟**商務用 Skype Server**的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="ad7e0-112">按一下 [**使用者**]，按一下 [**搜尋**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="ad7e0-113">選取您要移至商務用 Skype Server 2019 文件庫的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ad7e0-114">在這個範例中，我們將移動 [使用者 Sara Davis]。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="ad7e0-115">在 [**動作**] 功能表上，選取 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="ad7e0-116">從下拉式清單中，選取 [商務用 Skype Server 2019] 池。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="ad7e0-117">按一下 [**動作**]，然後按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="ad7e0-118">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="ad7e0-119">確認使用者的 [**註冊機構池**] 欄現在包含商務用 Skype Server 2019 pool，這表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="ad7e0-120">使用商務用 Skype Server 2019 管理命令介面來移動使用者</span><span class="sxs-lookup"><span data-stu-id="ad7e0-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="ad7e0-121">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ad7e0-122">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="ad7e0-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="ad7e0-123">接著，在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="ad7e0-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="ad7e0-124">**RegistrarPool**身分識別現在會指向商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ad7e0-125">此身分識別的狀態會確認使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="ad7e0-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ad7e0-126">如需**move-csuser** Cmdlet 的詳細資料，請執行： **Get-help move-csuser-詳細**資訊</span><span class="sxs-lookup"><span data-stu-id="ad7e0-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

