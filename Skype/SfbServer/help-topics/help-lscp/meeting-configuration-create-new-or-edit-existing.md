---
title: 會議設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 會議設定設定會為使用者排程的會議定義使用者加入體驗。 這些設定只適用于排程的會議。 在用戶端中按一下 [立即開會] 選項，不會套用至所建立的特定會議。
ms.openlocfilehash: 21cc12cd025edfc573e1e2f21ed08181f1a0c926
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099669"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="1fac7-105">會議組態：建立新的或編輯現有組態</span><span class="sxs-lookup"><span data-stu-id="1fac7-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="1fac7-106">會議設定設定會為使用者排程的會議定義使用者加入體驗。</span><span class="sxs-lookup"><span data-stu-id="1fac7-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="1fac7-107">這些設定只適用于排程的會議。</span><span class="sxs-lookup"><span data-stu-id="1fac7-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="1fac7-108">在用戶端中按一下 [ **立即開會** ] 選項，不會套用至所建立的特定會議。</span><span class="sxs-lookup"><span data-stu-id="1fac7-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1fac7-109">UI 參考</span><span class="sxs-lookup"><span data-stu-id="1fac7-109">UI Reference</span></span>

<span data-ttu-id="1fac7-110">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="1fac7-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1fac7-111">**範圍** 識別您要建立或修改之會議設定的範圍：全域、網站或集區。</span><span class="sxs-lookup"><span data-stu-id="1fac7-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="1fac7-112">**名稱** 會議設定預設會以名稱命名，無法變更其名稱。</span><span class="sxs-lookup"><span data-stu-id="1fac7-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="1fac7-113">**PSTN 呼叫者略過大廳** 選取此核取方塊，可自動承認透過公用交換電話網路 (PSTN) 電話線的方式撥打參加會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="1fac7-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="1fac7-114">清除此核取方塊可將 PSTN 來電者路由傳送到會議廳，直到會議簡報者授與會議的訪問權為止。</span><span class="sxs-lookup"><span data-stu-id="1fac7-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="1fac7-115">**指定為簡報者** 在會議召集人) 之外，選取使用者 (的類別，以在加入會議時自動將其指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="1fac7-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="1fac7-116">無論此設定為何，當會議排程時，簡報者都可以明確指定為簡報者，也可以在會議期間明確地將其提升為簡報者。</span><span class="sxs-lookup"><span data-stu-id="1fac7-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="1fac7-117">選項包括：</span><span class="sxs-lookup"><span data-stu-id="1fac7-117">The options are:</span></span>

  - <span data-ttu-id="1fac7-118">**無** 如果不是召集人的任何人自動指定為簡報者，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="1fac7-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="1fac7-119">**公司** 選取此選項可自動將組織的成員指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="1fac7-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="1fac7-120">**所有人** 選取此選項可自動將任何人指定為簡報者。</span><span class="sxs-lookup"><span data-stu-id="1fac7-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="1fac7-121">**依預設指派會議類型** 此設定會控制 Outlook 會議 Addin 是否一定要使用召集人指派的會議來排程會議，也就是說，已排程的會議一定會有相同的加入 URL 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="1fac7-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="1fac7-122">選取此核取方塊可讓已排程的會議永遠使用相同的 join URL。</span><span class="sxs-lookup"><span data-stu-id="1fac7-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="1fac7-123">清除此核取方塊可對每個會議使用不同的 join URL。</span><span class="sxs-lookup"><span data-stu-id="1fac7-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="1fac7-124">**預設會承認匿名使用者** 如果匿名 (（也就是未驗證的) 使用者預設會獲准參加會議），請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1fac7-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="1fac7-125">如果預設不允許匿名使用者參加會議，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1fac7-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="1fac7-126">**標誌 URL** 輸入包含要用於自訂會議邀請的圖像的 URL。</span><span class="sxs-lookup"><span data-stu-id="1fac7-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="1fac7-127">說明 **URL** 輸入使用者可取得加入會議協助的網站 URL。</span><span class="sxs-lookup"><span data-stu-id="1fac7-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="1fac7-128">**法律文字 URL** 輸入具有會議之法律資訊和免責聲明的網站 URL。</span><span class="sxs-lookup"><span data-stu-id="1fac7-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="1fac7-129">**自訂頁腳文字** 輸入要用於自訂會議邀請的文字。</span><span class="sxs-lookup"><span data-stu-id="1fac7-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="1fac7-130">如需使用會議設定的詳細資訊，請參閱作業文件中的＜[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)＞。</span><span class="sxs-lookup"><span data-stu-id="1fac7-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span> <span data-ttu-id="1fac7-131">如需針對大型會議設定會議設定的詳細資訊，請參閱規劃檔中的 [設定大型會議的支援](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) 。</span><span class="sxs-lookup"><span data-stu-id="1fac7-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in the Planning documentation.</span></span>