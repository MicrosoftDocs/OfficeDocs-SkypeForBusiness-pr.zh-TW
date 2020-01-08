---
title: (建議) 建立會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e912beac1eeffe3214f8a8d638926d84f547a270
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="82429-102">(建議) 建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="82429-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82429-103">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="82429-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="82429-104">在使用 Lync 2013 時，會議目錄會維持參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。</span><span class="sxs-lookup"><span data-stu-id="82429-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="82429-105">會議 ID 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="82429-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="82429-106">建立多個會議目錄可確保會議 Id 保持不變，直到建立大量的會議為止。</span><span class="sxs-lookup"><span data-stu-id="82429-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="82429-107">在每位使用者有典型會議數的組織中，我們建議您為池中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="82429-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="82429-108">使用這種準則，會議 Id 通常可以保持很小的狀態。</span><span class="sxs-lookup"><span data-stu-id="82429-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="82429-109">不過，一旦會議目錄數量（跨多個池）超過9個，會議 ID 長度就會增長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="82429-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="82429-110">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="82429-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="82429-111">在 Lync Server 管理命令介面中，輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="82429-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="82429-112">例如，下列程式會建立一個在 pool atl-cs-001.litwareinc.com 上託管的身分識別42的會議目錄：</span><span class="sxs-lookup"><span data-stu-id="82429-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82429-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="82429-113">See Also</span></span>


[<span data-ttu-id="82429-114">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="82429-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="82429-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="82429-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

