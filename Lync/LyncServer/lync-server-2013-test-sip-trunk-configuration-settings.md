---
title: Lync Server 2013：測試 SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f5357ae1a0dd4e8db044c2081154d4c3f4febf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="06684-102">在 Lync Server 2013 中測試 SIP 幹線配置設定</span><span class="sxs-lookup"><span data-stu-id="06684-102">Test SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06684-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="06684-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="06684-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="06684-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="06684-105">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="06684-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="06684-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="06684-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="06684-107">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="06684-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="06684-108">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="06684-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="06684-109">當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。</span><span class="sxs-lookup"><span data-stu-id="06684-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="06684-110">此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="06684-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="06684-111">系統管理員也可以使用 New-cstrunkconfiguration Cmdlet 來驗證主幹能將使用者撥出的號碼轉換成可由閘道處理的數位。</span><span class="sxs-lookup"><span data-stu-id="06684-111">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="06684-112">只能使用 Windows PowerShell 和[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) Cmdlet 來測試幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="06684-112">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="06684-113">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="06684-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="06684-114">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="06684-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="06684-115">測試 SIP 幹線設定設定</span><span class="sxs-lookup"><span data-stu-id="06684-115">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="06684-116">這個命令會驗證雷德蒙網站的幹線設定設定可以正確地轉換撥打的號碼4255551212。</span><span class="sxs-lookup"><span data-stu-id="06684-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

