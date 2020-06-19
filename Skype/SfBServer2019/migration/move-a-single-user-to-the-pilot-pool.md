---
title: 將單一使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將舊版集區中的使用者移至您的商務用 skype server 2019 試驗集區。 在下列範例中，在 [報名者集區] 欄中，pool01.contoso.net 為舊版集區，所有六個使用者都連接至此集區。 使用下列程式，透過商務用 Skype Server 2019 控制台和商務用 Skype Server 管理命令介面，將使用者移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752505"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="9226c-105">將單一使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="9226c-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="9226c-106">您可以使用商務用 Skype Server 2019 控制台或商務用 Skype Server 2019 管理命令介面，將舊版集區中的使用者移至您的商務用 skype server 2019 試驗集區。</span><span class="sxs-lookup"><span data-stu-id="9226c-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="9226c-107">在下列範例中，在 [**報名者集**區] 欄中， **pool01.contoso.net**為舊版集區，所有六個使用者都連接至此集區。</span><span class="sxs-lookup"><span data-stu-id="9226c-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="9226c-108">使用下列程式，透過商務用 Skype Server 2019 控制台和商務用 Skype Server 管理命令介面，將使用者移至商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="9226c-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="9226c-109">使用商務用 Skype Server 2019 控制台移動使用者</span><span class="sxs-lookup"><span data-stu-id="9226c-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="9226c-110">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9226c-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="9226c-111">開啟**商務用 Skype Server 控制台**。</span><span class="sxs-lookup"><span data-stu-id="9226c-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="9226c-112">按一下 [**使用者**]，按一下 [**搜尋**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="9226c-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="9226c-113">選取您要移至商務用 Skype Server 2019 集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="9226c-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9226c-114">在這個範例中，將移動使用者 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="9226c-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="9226c-115">在 [執行]\*\*\*\* 功能表上，選取 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9226c-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="9226c-116">從下拉式清單中，選取商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="9226c-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="9226c-117">按一下 [動作]\*\*\*\*，然後按一下 [將選取的使用者移至集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9226c-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="9226c-118">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9226c-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="9226c-119">確認使用者的 [**報名者集**區] 欄現在包含商務用 Skype Server 2019 集區，表示使用者已順利移動。</span><span class="sxs-lookup"><span data-stu-id="9226c-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="9226c-120">使用商務用 Skype Server 2019 管理命令介面移動使用者</span><span class="sxs-lookup"><span data-stu-id="9226c-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="9226c-121">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="9226c-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="9226c-122">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9226c-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="9226c-123">接著，在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="9226c-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="9226c-124">**RegistrarPool**身分識別現在會指向商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="9226c-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9226c-125">這個身分識別的出現表示已成功移動使用者。</span><span class="sxs-lookup"><span data-stu-id="9226c-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9226c-126">如需**Get-CsUser** Cmdlet 的詳細資訊，請執行： **Get-Help Get-CsUser 詳細**</span><span class="sxs-lookup"><span data-stu-id="9226c-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

