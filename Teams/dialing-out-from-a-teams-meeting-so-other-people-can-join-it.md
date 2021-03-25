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
description: 會議召集人可以瞭解如何使用 Teams 應用程式撥出，讓其他人使用他們的電話加入同一個會議。
ms.openlocfilehash: 55cbd5ccc9e9c364bcb829d9a392f61cbdd2f7f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119282"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="10b1f-103">從 Microsoft Teams 會議撥出，讓其他人可以加入會議</span><span class="sxs-lookup"><span data-stu-id="10b1f-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="10b1f-104">作為會議召集人，您可以使用 Teams 應用程式撥出，讓其他人使用他們的電話加入同一個會議。</span><span class="sxs-lookup"><span data-stu-id="10b1f-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="10b1f-105">當您撥出給某人時，建議您使用他們的完整電話號碼 (包括國家/地區代碼 - E.164 格式) 。</span><span class="sxs-lookup"><span data-stu-id="10b1f-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="10b1f-106">請注意：</span><span class="sxs-lookup"><span data-stu-id="10b1f-106">Please note that:</span></span>

- <span data-ttu-id="10b1f-107">您只有在使用 Teams 加入會議時才能撥出。</span><span class="sxs-lookup"><span data-stu-id="10b1f-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="10b1f-108">會議召集人已啟用音訊會議功能，或者，如果尚未指派音訊會議授權，則允許透過線上通話方案或直接路由撥打公用交換電話網絡。</span><span class="sxs-lookup"><span data-stu-id="10b1f-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="10b1f-109">會議召集人獲 [授予線上撥出政策，可啟用從會議撥出功能](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="10b1f-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="10b1f-110">以下是如何讓撥出工作：</span><span class="sxs-lookup"><span data-stu-id="10b1f-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="10b1f-111">**步驟 1：** 在會議中，使用新增人員按鈕選項的新增人員螢幕擷取畫面來撥出 ![ ](media/add-people-button.png) 到電話號碼。</span><span class="sxs-lookup"><span data-stu-id="10b1f-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="10b1f-112">**步驟 2：** 在邀請某人或撥打號碼方塊中輸入完整的電話號碼，包括國家/ **地區** 代碼。</span><span class="sxs-lookup"><span data-stu-id="10b1f-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![邀請某人或撥打號碼方塊的螢幕擷取畫面](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="10b1f-114">支援的國家/地區</span><span class="sxs-lookup"><span data-stu-id="10b1f-114">Supported countries and regions</span></span>

<span data-ttu-id="10b1f-115">撥出功能僅適用于部分國家/地區。</span><span class="sxs-lookup"><span data-stu-id="10b1f-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="10b1f-116">有關完整清單，請參閱音訊會議與通話方案的國家 [/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="10b1f-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="10b1f-117">允許使用者撥入</span><span class="sxs-lookup"><span data-stu-id="10b1f-117">Allow users to dial in</span></span>

<span data-ttu-id="10b1f-118">如果您正在尋找如何讓使用者撥入 Teams 會議的指示，請參閱 [Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)的音訊會議電話號碼。</span><span class="sxs-lookup"><span data-stu-id="10b1f-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="10b1f-119">想要進一瞭解音訊會議嗎？</span><span class="sxs-lookup"><span data-stu-id="10b1f-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="10b1f-120">嘗試或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="10b1f-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="10b1f-121">Microsoft Teams 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="10b1f-121">Microsoft Teams add-on licensing</span></span>](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)