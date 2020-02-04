---
title: 設定電話撥入式會議個人身分識別號碼（PIN）規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aef41f14b37d2a21fa747bb14132bd6e9ba93ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="df49d-102">在 Lync Server 2013 中設定電話撥入式會議個人身分識別號碼（PIN）規則</span><span class="sxs-lookup"><span data-stu-id="df49d-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df49d-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="df49d-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="df49d-104">在貴組織中擁有 Active Directory 網域服務（AD DS）認證的 Lync Server 2013 使用者，您可以使用個人識別碼（PIN），將電話撥入式會議加入為已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="df49d-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="df49d-105">PIN 原則定義電話撥入式會議 Pin 如何運作的規則。</span><span class="sxs-lookup"><span data-stu-id="df49d-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="df49d-106">如果您想要將特定原則套用至網站或特定使用者群組，您可以建立新的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="df49d-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="df49d-107">如果您想要為您的整個組織使用相同的 PIN 原則，您可以使用全域 PIN 原則，並視需要加以修改。</span><span class="sxs-lookup"><span data-stu-id="df49d-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="df49d-108">PIN 原則適用于最窄範圍的使用者到最廣泛的範圍。</span><span class="sxs-lookup"><span data-stu-id="df49d-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="df49d-109">如果您將使用者層級的 PIN 原則指派給使用者，這些設定就會優先。</span><span class="sxs-lookup"><span data-stu-id="df49d-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="df49d-110">如果您沒有指派使用者原則，就會套用網站層級的 PIN 原則（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="df49d-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="df49d-111">如果沒有適用的使用者或網站原則，全域 PIN 原則就會提供預設設定。</span><span class="sxs-lookup"><span data-stu-id="df49d-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df49d-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="df49d-112">In This Section</span></span>

  - [<span data-ttu-id="df49d-113">在 Lync Server 2013 中修改預設電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="df49d-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="df49d-114">在 Lync Server 2013 中建立或修改使用者站台或群組的電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="df49d-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="df49d-115">在 Lync Server 2013 中刪除網站或使用者群組的電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="df49d-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

