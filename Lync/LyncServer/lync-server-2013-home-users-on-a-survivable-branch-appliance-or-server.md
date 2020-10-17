---
title: Lync Server 2013： Survivable 分支裝置或伺服器上的家庭使用者
description: Lync Server 2013： Survivable 分支裝置或伺服器上的家庭使用者。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 124eb7a51a8d5ff672d720fdad8956f682e29090
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552779"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="dcb04-103">Lync Server 2013 的 Survivable 分支裝置或伺服器上的家庭使用者</span><span class="sxs-lookup"><span data-stu-id="dcb04-103">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcb04-104">_**主題上次修改日期：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="dcb04-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="dcb04-105">在 Survivable Branch 裝置或 Survivable Branch Server 上，將使用者上指的程式，類似于在前端集區上進行使用者的引導。</span><span class="sxs-lookup"><span data-stu-id="dcb04-105">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="dcb04-106">在中央網站執行 Survivable Branch 裝置或 Survivable Branch Server 程式。</span><span class="sxs-lookup"><span data-stu-id="dcb04-106">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="dcb04-107">在 Survivable Branch 裝置或 Survivable Branch Server 上的家庭使用者</span><span class="sxs-lookup"><span data-stu-id="dcb04-107">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="dcb04-108">將使用者移至 Survivable Branch Server 或 Survivable Branch 伺服器之前，請先開啟 Lync Server 管理命令介面，然後執行下列所有動作：</span><span class="sxs-lookup"><span data-stu-id="dcb04-108">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="dcb04-109">執行 Cmdlet **Test-CsPstnOutboundCall** ，確認 Survivable 分支伺服器正在執行，且已設定公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="dcb04-109">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="dcb04-110">如果您需要修改 PSTN 閘道屬性，請使用 Cmdlet **Set-CsPstnGateway**。</span><span class="sxs-lookup"><span data-stu-id="dcb04-110">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="dcb04-111">執行 Cmdlet **Get-CsVoicePolicy** ，確認將裝載在 Survivable Branch 伺服器上的使用者具有適當的 VoIP 路由原則。</span><span class="sxs-lookup"><span data-stu-id="dcb04-111">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="dcb04-112">如果您需要修改 VoIP 原則，請使用 Cmdlet **Set-CsVoicePolicy**。</span><span class="sxs-lookup"><span data-stu-id="dcb04-112">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="dcb04-113">執行 Cmdlet **Get-CsVoicemailReroutingConfiguration** ，確認已設定語音信箱重新路由設定。</span><span class="sxs-lookup"><span data-stu-id="dcb04-113">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="dcb04-114">如果您需要修改語音信箱重新路由設定，請使用 Cmdlet **Set-CsVoicemailReroutingConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="dcb04-114">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="dcb04-115">在 Lync Server 管理命令介面中，執行 Cmdlet **Move-CsUser** 以移動家用使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-115">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dcb04-116">您也可以使用 Lync Server 控制台來驗證必要條件和家用使用者。</span><span class="sxs-lookup"><span data-stu-id="dcb04-116">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dcb04-117">在 Lync Server Survivable Branch 裝置上的使用者無法建立新聊天室或查看現有聊天室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="dcb04-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcb04-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dcb04-118">See Also</span></span>


[<span data-ttu-id="dcb04-119">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="dcb04-119">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="dcb04-120">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="dcb04-120">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="dcb04-121">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="dcb04-121">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="dcb04-122">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="dcb04-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

