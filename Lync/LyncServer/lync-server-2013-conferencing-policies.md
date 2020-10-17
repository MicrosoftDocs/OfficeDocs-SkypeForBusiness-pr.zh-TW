---
title: Lync Server 2013：會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 681dbf0d6786656afcee12120e1b26d95bee41df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502300"
---
# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="d3adf-102">Lync Server 2013 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="d3adf-102">Conferencing policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3adf-103">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="d3adf-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="d3adf-p101">會議原則定義使用者可以在會議中使用的特性與功能。會議原則設定包含廣泛的排程和參與選項，從會議是否可包含 IP 音訊和視訊到可出席會議的人數上限都涵蓋在內。系統管理員可以使用會議原則來管理會議的安全、頻寬和法律層面。</span><span class="sxs-lookup"><span data-stu-id="d3adf-p101">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting). Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="d3adf-p102">您可在三個層級定義會議原則：通用範圍、站台範圍，以及使用者範圍。設定值會依據最窄的範圍到最寬的範圍，依序套用至特定使用者。如果將使用者原則指派給使用者，則這些設定具有優先權。如果未指派使用者原則，則會套用站台設定。如果未套用使用者或站台原則，則由通用原則提供預設值。</span><span class="sxs-lookup"><span data-stu-id="d3adf-p102">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a user policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="d3adf-p103">由於通用原則預設已經存在，因此您無法建立新的通用原則。您也無法刪除現有的通用原則，但您可以變更現有通用原則，自訂您自己的預設值。</span><span class="sxs-lookup"><span data-stu-id="d3adf-p103">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d3adf-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d3adf-114">In This Section</span></span>

  - [<span data-ttu-id="d3adf-115">在 Lync Server 2013 中查看會議原則資訊</span><span class="sxs-lookup"><span data-stu-id="d3adf-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="d3adf-116">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="d3adf-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="d3adf-117">在 Lync Server 2013 中刪除現有的會議原則</span><span class="sxs-lookup"><span data-stu-id="d3adf-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="d3adf-118">Lync Server 2013 的會議原則設定參考</span><span class="sxs-lookup"><span data-stu-id="d3adf-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

