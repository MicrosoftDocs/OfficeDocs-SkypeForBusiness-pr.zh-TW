---
title: Lync Server 2013：建立或修改會議裝置連絡人物件
description: Lync Server 2013：建立或修改會議裝置連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 853ee1c7dfda2fda99431b8cc1a5210a51f39a4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578009"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="4131d-103">在 Lync Server 2013 中建立或修改會議裝置連絡人物件</span><span class="sxs-lookup"><span data-stu-id="4131d-103">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4131d-104">_**主題上次修改日期：** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="4131d-104">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="4131d-105">若要建立會議聊天室物件，請先建立 Active Directory 使用者帳戶來代表裝置。</span><span class="sxs-lookup"><span data-stu-id="4131d-105">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="4131d-106">然後，使用 **Enable-CsMeetingRoom** Cmdlet 以啟用該帳戶充當會議裝置。</span><span class="sxs-lookup"><span data-stu-id="4131d-106">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="4131d-107">如果您需要變更現有會議裝置的屬性，請使用 **Set-CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4131d-107">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="4131d-108">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4131d-108">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4131d-109">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="4131d-109">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="4131d-110">建立會議裝置</span><span class="sxs-lookup"><span data-stu-id="4131d-110">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="4131d-111">在您建立代表新會議裝置的 Active Directory 使用者帳戶之後，使用 **Enable-CsMeetingRoom** Cmdlet 來啟用它。</span><span class="sxs-lookup"><span data-stu-id="4131d-111">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="4131d-112">請務必加入) 會議裝置身分識別、b) 會議室帳戶所在的註冊機構集區，以及 c) 指派給該帳戶的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4131d-112">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="4131d-113">例如：</span><span class="sxs-lookup"><span data-stu-id="4131d-113">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="4131d-114">修改會議裝置</span><span class="sxs-lookup"><span data-stu-id="4131d-114">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="4131d-115">若要修改現有會議裝置的屬性值，請使用 **Set-CsMeetingRoom** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4131d-115">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="4131d-116">例如，下列命令會更新與會議裝置相關聯的電話號碼 (LineUri) ：</span><span class="sxs-lookup"><span data-stu-id="4131d-116">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="4131d-117">如需詳細資訊，請參閱 [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 及 [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="4131d-117">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

