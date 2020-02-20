---
title: （建議使用）建立會議目錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77688be2f2b1ba547f79e45ca89dd529e24318c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="6ccdf-102">（建議使用）建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="6ccdf-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ccdf-103">_**上次修改主題：** 2014年-10-03_</span><span class="sxs-lookup"><span data-stu-id="6ccdf-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="6ccdf-104">會議目錄維護參與者使用時使用 Lync 2013 加入會議的英數字元的會議 ID 與電話撥入式會議參與者加入會議所使用的僅限數字鍵台的會議 ID 之間的對應。</span><span class="sxs-lookup"><span data-stu-id="6ccdf-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="6ccdf-105">會議 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="6ccdf-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="6ccdf-106">建立多個會議目錄，可確保在建立大量的會議之前會議 Id 會保持簡短。</span><span class="sxs-lookup"><span data-stu-id="6ccdf-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="6ccdf-107">在一般每位使用者的會議數目與組織中，我們建議您在集區中建立一個的每個 999 使用者的會議目錄。</span><span class="sxs-lookup"><span data-stu-id="6ccdf-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="6ccdf-108">使用此指導方針會議識別碼可以通常是保持小型。</span><span class="sxs-lookup"><span data-stu-id="6ccdf-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="6ccdf-109">不過，一旦 （整個集區） 的會議目錄的數目超過 9，會議 ID 長度會成長到支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="6ccdf-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="6ccdf-110">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="6ccdf-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="6ccdf-111">在 [Lync Server 管理命令介面，輸入下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6ccdf-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="6ccdf-112">例如，下列範例會建立裝載在 atl-cs-001.litwareinc.com 集區身分識別 42，會議目錄-atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="6ccdf-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ccdf-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ccdf-113">See Also</span></span>


[<span data-ttu-id="6ccdf-114">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="6ccdf-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="6ccdf-115">新 CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="6ccdf-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

