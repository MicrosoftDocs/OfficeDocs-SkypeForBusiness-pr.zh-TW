---
title: Lync Server 2013：查看常見的區域電話資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38614b2993ddd9ad3fe3a662a334440a1d1287b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="f67ca-102">在 Lync Server 2013 中查看常見區域電話資訊</span><span class="sxs-lookup"><span data-stu-id="f67ca-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f67ca-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f67ca-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f67ca-104">您可以透過**CsCommonAreaPhone** Cmdlet，查看設定為在您的組織中使用之通用區域電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f67ca-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="f67ca-105">如果在沒有任何參數的情況下使用，這個 Cmdlet 會傳回所有您所有常見區域手機的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f67ca-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="f67ca-106">選用的參數提供不同的方式來篩選資訊。</span><span class="sxs-lookup"><span data-stu-id="f67ca-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="f67ca-107">例如，您可以傳回在指定組織單位（OU）中有連絡人物件的所有常見區域電話，或是指定建築物中的所有連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="f67ca-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="f67ca-108">如需**取得 CsCommonAreaPhone**參數的詳細資訊，請參閱[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="f67ca-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="f67ca-109">從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行**CsCommonAreaPhone** 。</span><span class="sxs-lookup"><span data-stu-id="f67ca-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="f67ca-110">查看所有常用區域手機的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f67ca-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="f67ca-111">若要查看所有常見區域手機的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="f67ca-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="f67ca-112">您會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="f67ca-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="f67ca-113">如需詳細資訊，請參閱[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f67ca-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

