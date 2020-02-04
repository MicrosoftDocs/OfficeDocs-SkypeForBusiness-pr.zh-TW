---
title: Lync Server 2013：啟用或停用會議裝置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="ba74e-102">在 Lync Server 2013 中啟用或停用會議裝置</span><span class="sxs-lookup"><span data-stu-id="ba74e-102">Enable or disable a conferencing device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba74e-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ba74e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ba74e-104">使用**enable-CsMeetingRoom** Cmdlet 和**disable CsMeetingRoom** Cmdlet 來啟用和停用會議裝置。</span><span class="sxs-lookup"><span data-stu-id="ba74e-104">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="ba74e-105">這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="ba74e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba74e-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="ba74e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="ba74e-107">啟用會議裝置</span><span class="sxs-lookup"><span data-stu-id="ba74e-107">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="ba74e-108">若要啟用會議裝置，請使用**enable-CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ba74e-108">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="ba74e-109">啟用會議裝置時，您必須包含一個）會議裝置身分識別、b）房間帳戶所在的註冊機構池，以及 c）要指派給該帳戶的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="ba74e-109">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="ba74e-110">停用會議裝置</span><span class="sxs-lookup"><span data-stu-id="ba74e-110">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="ba74e-111">若要停用會議裝置，請使用**Disable CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ba74e-111">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="ba74e-112">請務必指定要停用的會議裝置身分識別：</span><span class="sxs-lookup"><span data-stu-id="ba74e-112">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="ba74e-113">如需詳細資訊，請參閱[Enable CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 和[Disable CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ba74e-113">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

