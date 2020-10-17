---
title: " (建議) 建立會議目錄"
description: " (建議) 建立會議目錄。"
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b14982893fbc14a87818875a787d0f776da84ae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563659"
---
# <a name="recommended-create-conference-directories"></a><span data-ttu-id="29fb1-103"> (建議) 建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="29fb1-103">(Recommended) Create Conference Directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29fb1-104">_**主題上次修改日期：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="29fb1-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="29fb1-105">會議目錄會維護在使用 Lync 2013 時，參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="29fb1-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="29fb1-106">會議識別碼的格式如下：</span><span class="sxs-lookup"><span data-stu-id="29fb1-106">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="29fb1-107">建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。</span><span class="sxs-lookup"><span data-stu-id="29fb1-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="29fb1-108">在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="29fb1-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="29fb1-109">使用此指導方針時，會議 IDs 通常可以保持很小。</span><span class="sxs-lookup"><span data-stu-id="29fb1-109">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="29fb1-110">不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼長度就會成長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="29fb1-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="29fb1-111">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="29fb1-111">Creating a conference directory</span></span>

1.  <span data-ttu-id="29fb1-112">在 Lync Server 管理命令介面中，輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="29fb1-112">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="29fb1-113">例如，下列所建立的會議目錄使用 identity 42，主控于集區 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="29fb1-113">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29fb1-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="29fb1-114">See Also</span></span>


[<span data-ttu-id="29fb1-115">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="29fb1-115">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="29fb1-116">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="29fb1-116">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

