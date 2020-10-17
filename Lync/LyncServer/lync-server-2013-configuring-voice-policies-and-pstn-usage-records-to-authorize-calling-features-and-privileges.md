---
title: Lync Server 2013：設定語音原則和 PSTN 使用方式記錄，以授權通話功能和許可權
description: Lync Server 2013：設定語音原則和 PSTN 使用方式記錄，以授權通話功能和許可權。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a12c9c64c3f02effba7c7709321eda91350ebb75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542279"
---
# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="242d3-103">在 Lync Server 2013 中設定語音原則和 PSTN 使用方式記錄，以授權呼叫功能和許可權</span><span class="sxs-lookup"><span data-stu-id="242d3-103">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="242d3-104">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="242d3-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="242d3-105">*「語音原則」* 會啟用一組撥號功能，並關聯一或多個 PSTN 使用方式記錄，以定義已指派原則之使用者的撥號功能及權限。</span><span class="sxs-lookup"><span data-stu-id="242d3-105">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="242d3-p101">語音原則範圍可以是「網站」\*\*(定義網站的預設功能及權限) 或 *「使用者」*(定義要根據個別使用者或群組指派的功能及權限)。未指派給語音原則的使用者會自動指派給全域原則 (其為與產品一起安裝的預設語音原則)。</span><span class="sxs-lookup"><span data-stu-id="242d3-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="242d3-108">如需詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-voice-policies.md">Lync Server 2013 中的語音原則</A> 。</span><span class="sxs-lookup"><span data-stu-id="242d3-108">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="242d3-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="242d3-109">In This Section</span></span>

  - [<span data-ttu-id="242d3-110">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="242d3-110">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="242d3-111">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="242d3-111">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="242d3-112">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="242d3-112">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

