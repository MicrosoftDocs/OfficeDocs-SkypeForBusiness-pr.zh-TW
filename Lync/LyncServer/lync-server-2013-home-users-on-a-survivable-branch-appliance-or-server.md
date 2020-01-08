---
title: Lync Server 2013：將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="ea25c-102">在 Lync Server 2013 中將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ea25c-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea25c-103">_**主題上次修改日期：** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="ea25c-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="ea25c-104">將使用者放在 Survivable 分支裝置或 Survivable 分支伺服器的程式，與將使用者放在前端池中的程式類似。</span><span class="sxs-lookup"><span data-stu-id="ea25c-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="ea25c-105">在中央網站執行 Survivable 分支裝置或 Survivable 分支伺服器程式。</span><span class="sxs-lookup"><span data-stu-id="ea25c-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="ea25c-106">Survivable 分支裝置或 Survivable 分支伺服器上的家用使用者</span><span class="sxs-lookup"><span data-stu-id="ea25c-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="ea25c-107">在將使用者移至 Survivable 分支伺服器或 Survivable 分支伺服器之前，請先開啟 Lync Server 管理命令介面，然後執行下列所有動作：</span><span class="sxs-lookup"><span data-stu-id="ea25c-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="ea25c-108">執行 Cmdlet**測試-CsPstnOutboundCall** ，以驗證 Survivable 分支伺服器是否正在執行，以及是否已設定公用交換電話網絡（PSTN）連線。</span><span class="sxs-lookup"><span data-stu-id="ea25c-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="ea25c-109">如果您需要修改 PSTN 閘道屬性，請使用 Cmdlet **CsPstnGateway**。</span><span class="sxs-lookup"><span data-stu-id="ea25c-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="ea25c-110">執行 Cmdlet **CsVoicePolicy** ，確認將駐留在 Survivable 分支伺服器的使用者具有適當的 VoIP 路由原則。</span><span class="sxs-lookup"><span data-stu-id="ea25c-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="ea25c-111">如果您需要修改 VoIP 原則，請使用 Cmdlet **CsVoicePolicy**。</span><span class="sxs-lookup"><span data-stu-id="ea25c-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="ea25c-112">執行 Cmdlet **CsVoicemailReroutingConfiguration** ，確認已設定語音信箱重新路由設定。</span><span class="sxs-lookup"><span data-stu-id="ea25c-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="ea25c-113">如果您需要修改語音信箱重新路由設定，請使用 Cmdlet **CsVoicemailReroutingConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="ea25c-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="ea25c-114">在 Lync Server 管理命令介面中，執行 Cmdlet**移動 move-csuser**以移動家用使用者。</span><span class="sxs-lookup"><span data-stu-id="ea25c-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ea25c-115">您也可以使用 Lync Server [控制台] 驗證系統必備與家用使用者。</span><span class="sxs-lookup"><span data-stu-id="ea25c-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ea25c-116">駐留在 Lync Server Survivable 分支裝置上的使用者無法建立新的聊天室，或無法查看現有聊天室的聊天室卡片。</span><span class="sxs-lookup"><span data-stu-id="ea25c-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea25c-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="ea25c-117">See Also</span></span>


[<span data-ttu-id="ea25c-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="ea25c-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="ea25c-119">CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="ea25c-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="ea25c-120">CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea25c-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="ea25c-121">移動流覽 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="ea25c-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

