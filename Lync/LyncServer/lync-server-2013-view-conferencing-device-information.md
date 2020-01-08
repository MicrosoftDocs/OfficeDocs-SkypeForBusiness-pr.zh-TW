---
title: Lync Server 2013：查看會議裝置資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4b40e0ee28f13aa6be52009b750258c5cdadffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="bae3c-102">在 Lync Server 2013 中查看會議裝置資訊</span><span class="sxs-lookup"><span data-stu-id="bae3c-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bae3c-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bae3c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bae3c-104">您可以使用 Windows PowerShell 及**CsMeetingRoom** Cmdlet 來查看已設定為在您的組織中使用之會議裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bae3c-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="bae3c-105">從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行**CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bae3c-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bae3c-106">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="bae3c-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="bae3c-107">如果您使用不含任何參數的**CsMeetingRoom** Cmdlet，則會傳回所有會議裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bae3c-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="bae3c-108">選用的參數提供不同的方式來篩選資訊。</span><span class="sxs-lookup"><span data-stu-id="bae3c-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="bae3c-109">如需詳細資訊，請參閱[取得 CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的參數區段。</span><span class="sxs-lookup"><span data-stu-id="bae3c-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="bae3c-110">查看所有會議裝置的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bae3c-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="bae3c-111">若要查看所有會議裝置的詳細資料，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="bae3c-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="bae3c-112">這個 Cmdlet 會針對每個會議裝置傳回如下所示的資訊。</span><span class="sxs-lookup"><span data-stu-id="bae3c-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="bae3c-113">請注意，這個範例只會顯示您執行此 Cmdlet 時所看到的部分資訊：</span><span class="sxs-lookup"><span data-stu-id="bae3c-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="bae3c-114">查看特定會議裝置的相關資訊</span><span class="sxs-lookup"><span data-stu-id="bae3c-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="bae3c-115">若要查看特定會議裝置的相關資訊，請在身分識別參數後加上會議裝置身分識別（通常是 Active Directory 顯示名稱）。</span><span class="sxs-lookup"><span data-stu-id="bae3c-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="bae3c-116">例如：</span><span class="sxs-lookup"><span data-stu-id="bae3c-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="bae3c-117">如需詳細資訊，請參閱[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bae3c-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

