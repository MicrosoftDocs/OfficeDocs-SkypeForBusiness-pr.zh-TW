---
title: 設定電話撥入式會議個人識別碼 (pin) 規則
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
ms.openlocfilehash: 27a2298dffdcb868646f2d4d4513702a4c4554d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="11235-102">在 Lync Server 2013 中設定電話撥入式會議個人識別碼 (pin) 規則</span><span class="sxs-lookup"><span data-stu-id="11235-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11235-103">_**主題上次修改日期：** 2012年-06-19_</span><span class="sxs-lookup"><span data-stu-id="11235-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="11235-104">在您的組織中具有 Active Directory 網域服務 (AD DS) 認證的 Lync Server 2013 使用者可以為已驗證的使用者加入電話撥入式會議使用個人識別碼 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="11235-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="11235-105">PIN 原則可定義電話撥入式會議 PIN 的運作方式規則。</span><span class="sxs-lookup"><span data-stu-id="11235-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="11235-p102">如果您要將特定原則套用至網站或特定使用者群組，您可以建立新的 PIN 原則。如果您要對整個組織使用相同的 PIN 原則，您可以使用全域 PIN 原則，並視需要加以修改。對使用者套用 PIN 原則時，會優先套用最小的範圍。如果您為使用者指派了使用者層級 PIN 原則，這些設定將會優先套用。如果您未指派使用者原則，則會套用網站層級 PIN 原則 (若有的話)。如果未套用使用者或網站原則，則會使用全域 PIN 原則的預設設定。</span><span class="sxs-lookup"><span data-stu-id="11235-p102">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users. If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. PIN policies apply to users from the narrowest scope to the widest scope. If you assign a user-level PIN policy to a user, those settings take precedence. If you do not assign a user policy, the site-level PIN policy applies, if it exists. If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11235-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="11235-112">In This Section</span></span>

  - [<span data-ttu-id="11235-113">修改預設電話撥入式會議 PIN 設定 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="11235-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="11235-114">建立或修改電話撥入式會議 PIN 設定 Lync Server 2013 中的網站或使用者群組</span><span class="sxs-lookup"><span data-stu-id="11235-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="11235-115">刪除網站或 Lync Server 2013 中的使用者群組的電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="11235-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

