---
title: 從會議撥出，讓其他人可以加入
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 會議召集人可以瞭解如何使用 [團隊] 應用程式撥出，讓其他人使用自己的手機加入相同的會議。
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788757"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="94ee0-103">從 Microsoft 團隊會議撥出，讓其他人可以加入</span><span class="sxs-lookup"><span data-stu-id="94ee0-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="94ee0-104">就像會議召集人一樣，您可以使用 [小組] 應用程式撥出，讓其他人使用自己的手機加入相同的會議。</span><span class="sxs-lookup"><span data-stu-id="94ee0-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="94ee0-105">當您向某人撥出時，建議您使用完整的電話號碼來執行， (包括國家/地區碼-E. 164 格式) 。</span><span class="sxs-lookup"><span data-stu-id="94ee0-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="94ee0-106">請注意：</span><span class="sxs-lookup"><span data-stu-id="94ee0-106">Please note that:</span></span>

- <span data-ttu-id="94ee0-107">您只能在使用小組加入會議時撥出。</span><span class="sxs-lookup"><span data-stu-id="94ee0-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="94ee0-108">會議召集人已啟用音訊會議，或者在未指派音訊會議授權的情況下，您可以透過線上通話方案或直接路由撥打電話給公用交換電話網絡。</span><span class="sxs-lookup"><span data-stu-id="94ee0-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="94ee0-109">已授與會議召集人的 [線上撥出原則，允許從會議撥出](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="94ee0-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="94ee0-110">以下說明如何開始撥出作業：</span><span class="sxs-lookup"><span data-stu-id="94ee0-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="94ee0-111">**步驟1：** 在會議中，使用 [新增人員] 按鈕選項的 [ **新增人員**] ![ 螢幕擷取畫面 ](media/add-people-button.png) 撥出電話號碼。</span><span class="sxs-lookup"><span data-stu-id="94ee0-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="94ee0-112">**步驟2：** 輸入完整的電話號碼，包括 [ **邀請某人或撥打電話號碼** ] 方塊中的國家/地區碼。</span><span class="sxs-lookup"><span data-stu-id="94ee0-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![[邀請某人或撥打電話號碼] 方塊的螢幕擷取畫面](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="94ee0-114">支援的國家和地區</span><span class="sxs-lookup"><span data-stu-id="94ee0-114">Supported countries and regions</span></span>

<span data-ttu-id="94ee0-115">撥出功能只適用于部分國家/地區。</span><span class="sxs-lookup"><span data-stu-id="94ee0-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="94ee0-116">如需完整清單，請參閱 [音訊會議與通話方案的國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="94ee0-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="94ee0-117">允許使用者撥入</span><span class="sxs-lookup"><span data-stu-id="94ee0-117">Allow users to dial in</span></span>

<span data-ttu-id="94ee0-118">如果您正在尋找如何讓您的使用者撥入團隊會議的指示，請參閱 [Microsoft 團隊中的音訊會議電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="94ee0-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="94ee0-119">想要深入瞭解音訊會議嗎？</span><span class="sxs-lookup"><span data-stu-id="94ee0-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="94ee0-120">試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="94ee0-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="94ee0-121">Microsoft Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="94ee0-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
