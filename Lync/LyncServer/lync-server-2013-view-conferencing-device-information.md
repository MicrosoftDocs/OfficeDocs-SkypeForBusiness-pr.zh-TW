---
title: Lync Server 2013：查看會議裝置資訊
description: Lync Server 2013：查看會議裝置資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bbbdcecbc15ef59b2b9e22ffd2b28ff745d67a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574769"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="a36d3-103">在 Lync Server 2013 中查看會議裝置資訊</span><span class="sxs-lookup"><span data-stu-id="a36d3-103">View conferencing device information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a36d3-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a36d3-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a36d3-105">您可以使用 Windows PowerShell 和 **Get-CsMeetingRoom** 指令程式，來查看已設定供組織使用之會議裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a36d3-105">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="a36d3-106">從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行 **Get-CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a36d3-106">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a36d3-107">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="a36d3-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="a36d3-108">如果您使用不含任何參數的 **Get-CsMeetingRoom** Cmdlet，它會傳回所有會議裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a36d3-108">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="a36d3-109">選用參數提供不同的篩選資訊的方式。</span><span class="sxs-lookup"><span data-stu-id="a36d3-109">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="a36d3-110">如需詳細資訊，請參閱 [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的 [參數] 區段。</span><span class="sxs-lookup"><span data-stu-id="a36d3-110">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="a36d3-111">查看所有會議裝置的相關資訊</span><span class="sxs-lookup"><span data-stu-id="a36d3-111">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="a36d3-112">若要查看所有會議裝置的詳細資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a36d3-112">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="a36d3-113">此 Cmdlet 會針對每個會議裝置傳回類似下列的資訊。</span><span class="sxs-lookup"><span data-stu-id="a36d3-113">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="a36d3-114">請注意，此範例只會顯示您執行此 Cmdlet 時所看到的部分資訊：</span><span class="sxs-lookup"><span data-stu-id="a36d3-114">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="a36d3-115">查看特定會議裝置的相關資訊</span><span class="sxs-lookup"><span data-stu-id="a36d3-115">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="a36d3-116">若要查看特定會議裝置的資訊，請在識別參數後面加上會議裝置身分識別 (通常是 Active Directory 顯示名稱) 。</span><span class="sxs-lookup"><span data-stu-id="a36d3-116">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="a36d3-117">例如：</span><span class="sxs-lookup"><span data-stu-id="a36d3-117">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="a36d3-118">如需詳細資訊，請參閱 [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="a36d3-118">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

