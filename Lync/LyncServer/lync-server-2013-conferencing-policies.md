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
ms.openlocfilehash: 96d1d9ed6fc0ad75e316a41ef7939f36ecaba354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="fc575-102">Lync Server 2013 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="fc575-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc575-103">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="fc575-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="fc575-104">會議原則定義使用者在會議（也稱為會議）期間可使用的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="fc575-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="fc575-105">會議原則設定包含各種排程和參與選項，包括從會議是否可以將 IP 音訊與影片加入到可參與的人數上限。</span><span class="sxs-lookup"><span data-stu-id="fc575-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="fc575-106">系統管理員可以使用會議原則來管理會議的安全性、頻寬和法律方面。</span><span class="sxs-lookup"><span data-stu-id="fc575-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="fc575-107">您可以在三個層級定義會議原則：全域範圍、網站範圍和使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="fc575-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="fc575-108">[設定] 會將最窄範圍的特定使用者套用至最廣泛的範圍。</span><span class="sxs-lookup"><span data-stu-id="fc575-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="fc575-109">如果您將使用者原則指派給使用者，這些設定就會優先。</span><span class="sxs-lookup"><span data-stu-id="fc575-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="fc575-110">如果您沒有指派使用者原則，就會套用 [網站設定]。</span><span class="sxs-lookup"><span data-stu-id="fc575-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="fc575-111">如果沒有適用的使用者或網站原則，全域原則就會提供預設設定。</span><span class="sxs-lookup"><span data-stu-id="fc575-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="fc575-112">全域原則預設存在，所以您無法建立新的全域原則。</span><span class="sxs-lookup"><span data-stu-id="fc575-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="fc575-113">您也無法刪除現有的全域原則，但您可以變更現有的全域原則，來自訂您的預設設定。</span><span class="sxs-lookup"><span data-stu-id="fc575-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fc575-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="fc575-114">In This Section</span></span>

  - [<span data-ttu-id="fc575-115">在 Lync Server 2013 中查看會議原則資訊</span><span class="sxs-lookup"><span data-stu-id="fc575-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="fc575-116">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="fc575-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="fc575-117">刪除 Lync Server 2013 中的現有會議原則</span><span class="sxs-lookup"><span data-stu-id="fc575-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="fc575-118">Lync Server 2013 的會議原則設定參考</span><span class="sxs-lookup"><span data-stu-id="fc575-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

