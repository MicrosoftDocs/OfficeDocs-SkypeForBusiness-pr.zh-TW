---
title: '[會議設定] 建立新的或 [編輯現有]'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: '[會議設定] 設定會為使用者排程的會議定義使用者的加入體驗。 這些設定僅適用于排程的會議。 它們不適用於在用戶端中按一下 [立即開會] 選項所建立的即席會議。'
ms.openlocfilehash: 002550fadb845a15178567a62ad3189df7d652ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193202"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="31c64-105">會議組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="31c64-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="31c64-p102">會議組態設定會定義由使用者安排之會議的使用者加入體驗。這些設定只適用於事先安排的會議，不適用於透過按一下用戶端中的 [立即開會]\*\*\*\* 選項所建立的臨時會議。</span><span class="sxs-lookup"><span data-stu-id="31c64-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="31c64-109">UI 參考</span><span class="sxs-lookup"><span data-stu-id="31c64-109">UI Reference</span></span>

<span data-ttu-id="31c64-110">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="31c64-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="31c64-111">**範圍**識別您要建立或修改的會議設定範圍: [全域]、[網站] 或 [文件庫]。</span><span class="sxs-lookup"><span data-stu-id="31c64-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="31c64-112">**名稱**會議配置預設會命名, 且無法變更名稱。</span><span class="sxs-lookup"><span data-stu-id="31c64-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="31c64-113">**PSTN 呼叫者略過大廳**選取此核取方塊, 以自動准許使用公用交換電話網絡 (PSTN) 電話線路撥入會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="31c64-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="31c64-114">清除此核取方塊可將 PSTN 呼叫者路由到會議廳, 直到會議簡報者准許他們存取會議為止。</span><span class="sxs-lookup"><span data-stu-id="31c64-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="31c64-115">**指定為簡報者**選取使用者類別 (除了會議召集人), 在加入會議時, 系統會自動將其指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="31c64-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="31c64-116">無論這項設定為何, 在排程會議時, 簡報者都可以明確指定為簡報者, 或者可以在會議期間明確地將其升級為簡報者。</span><span class="sxs-lookup"><span data-stu-id="31c64-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="31c64-117">選項包括:</span><span class="sxs-lookup"><span data-stu-id="31c64-117">The options are:</span></span>

  - <span data-ttu-id="31c64-118">**None**如果召集人以外的任何人都不會自動指定為簡報者, 請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="31c64-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="31c64-119">**公司**選取這個選項, 即可自動將組織的成員指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="31c64-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="31c64-120">**所有人**選取此選項可自動將任何人指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="31c64-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="31c64-121">**預設為指派的會議類型**此設定會控制 Outlook 會議增益集是否總是使用召集人指派的會議來排程會議, 這表示排程的會議永遠具有相同的聯接 URL 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="31c64-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="31c64-122">選取此核取方塊可讓排程的會議永遠使用相同的聯接 URL。</span><span class="sxs-lookup"><span data-stu-id="31c64-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="31c64-123">清除此核取方塊, 以針對每個會議使用不同的加入 URL。</span><span class="sxs-lookup"><span data-stu-id="31c64-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="31c64-124">**預設會承認匿名使用者**如果是匿名 (也就是未獲驗證), 允許使用者預設出席會議, 請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="31c64-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="31c64-125">如果預設不允許匿名使用者出席會議, 請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="31c64-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="31c64-126">**標誌 URL**輸入包含要用於自訂會議邀請之圖像的 URL。</span><span class="sxs-lookup"><span data-stu-id="31c64-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="31c64-127">說明**URL**輸入網站的 URL, 使用者可以在此取得加入會議的協助。</span><span class="sxs-lookup"><span data-stu-id="31c64-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="31c64-128">**法律文字 URL**輸入含有該會議之法律資訊和免責聲明的網站 URL。</span><span class="sxs-lookup"><span data-stu-id="31c64-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="31c64-129">**自訂頁尾文字**輸入要在自訂會議邀請上使用的文字。</span><span class="sxs-lookup"><span data-stu-id="31c64-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="31c64-p107">如需使用會議設定的詳細資訊，請參閱作業文件中的〈[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)〉如需設定大型會議之會議設定的詳細資訊，請參閱規劃文件中的〈[Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="31c64-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


