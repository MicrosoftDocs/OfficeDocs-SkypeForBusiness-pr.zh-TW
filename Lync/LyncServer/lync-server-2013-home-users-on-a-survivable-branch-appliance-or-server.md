---
title: Survivable Branch Appliance 或 Server 上的 Lync Server 2013： 首頁使用者
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
ms.openlocfilehash: c6efd5991260ffeec3c6279857625eadfe34eca4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="5d514-102">使用者隸屬於 Survivable Branch Appliance 或 Lync Server 2013 中的伺服器</span><span class="sxs-lookup"><span data-stu-id="5d514-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d514-103">_**上次修改主題：** 2014年-12-10_</span><span class="sxs-lookup"><span data-stu-id="5d514-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="5d514-104">首頁的程序 Survivable Branch Appliance 或 Survivable Branch 伺服器上的使用者是類似隸屬使用者的程序上的前端集區。</span><span class="sxs-lookup"><span data-stu-id="5d514-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="5d514-105">執行 Survivable Branch Appliance 或 Survivable Branch 伺服器的程序在中央網站。</span><span class="sxs-lookup"><span data-stu-id="5d514-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="5d514-106">將使用者隸屬於 Survivable Branch Appliance 或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="5d514-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="5d514-107">之前將使用者移至 Survivable Branch 伺服器或 Survivable Branch 伺服器，開啟 [Lync Server 管理命令介面中，，然後執行下列各項：</span><span class="sxs-lookup"><span data-stu-id="5d514-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="5d514-108">執行指令程式**Test-cspstnoutboundcall**若要確認 Survivable Branch 伺服器正在執行，而且已公用交換電話網路 (PSTN) 連線能力。</span><span class="sxs-lookup"><span data-stu-id="5d514-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="5d514-109">如果您要修改 PSTN 閘道內容，使用**Set-cspstngateway**cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5d514-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="5d514-110">執行指令程式**Get-csvoicepolicy**驗證將會位於 Survivable Branch 伺服器的使用者具備適當的 VoIP 路由原則。</span><span class="sxs-lookup"><span data-stu-id="5d514-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="5d514-111">如果您要修改的 VoIP 原則，使用 cmdlet **Set-csvoicepolicy**。</span><span class="sxs-lookup"><span data-stu-id="5d514-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="5d514-112">執行指令程式**Get-csvoicemailreroutingconfiguration**若要確認已設定語音信箱重新設定。</span><span class="sxs-lookup"><span data-stu-id="5d514-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="5d514-113">如果您要修改語音信箱重新路由設定，使用 cmdlet**設定 CsVoicemailReroutingConfiguration**。</span><span class="sxs-lookup"><span data-stu-id="5d514-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="5d514-114">在 Lync Server 管理命令介面中，執行 cmdlet **Move-csuser**以移動隸屬使用者。</span><span class="sxs-lookup"><span data-stu-id="5d514-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d514-115">您也可以使用 Lync Server 控制台來確認先決條件並隸屬使用者。</span><span class="sxs-lookup"><span data-stu-id="5d514-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5d514-116">位於 Lync Server Survivable Branch Appliance 的使用者將無法建立新聊天室或檢視現有的會議室的會議室卡片。</span><span class="sxs-lookup"><span data-stu-id="5d514-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d514-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5d514-117">See Also</span></span>


[<span data-ttu-id="5d514-118">Test-cspstnoutboundcall</span><span class="sxs-lookup"><span data-stu-id="5d514-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="5d514-119">Get-csvoicepolicy</span><span class="sxs-lookup"><span data-stu-id="5d514-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="5d514-120">Get-csvoicemailreroutingconfiguration</span><span class="sxs-lookup"><span data-stu-id="5d514-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="5d514-121">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="5d514-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

