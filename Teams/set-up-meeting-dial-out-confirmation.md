---
title: 在 Microsoft Teams 中為使用者設定會議撥出確認
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何設定 Teams 以要求撥出確認，以防止語音信箱系統在被叫人無法接聽電話時連接到會議。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117091"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="89d28-103">在 Microsoft Teams 中為使用者設定會議撥出確認</span><span class="sxs-lookup"><span data-stu-id="89d28-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="89d28-104">會議撥出和撥打電話給我是邀請參與者加入會議，以及現有參與者使用傳統或行動電話加入會議非常有用的方式。</span><span class="sxs-lookup"><span data-stu-id="89d28-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="89d28-105">不過，當通話者無法接聽來電，且語音信箱系統接聽來電時，語音信箱系統會連接到會議，參與者將能夠聆聽，直到會議移除。</span><span class="sxs-lookup"><span data-stu-id="89d28-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="89d28-106">若要防止語音信箱系統在撥出會議時連到會議，而電話撥入者無法接聽電話，您可以設定 Teams，要求被叫人確認他們加入會議。</span><span class="sxs-lookup"><span data-stu-id="89d28-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="89d28-107">如果來電者無法接聽來電，且語音信箱系統接聽來電，語音信箱系統將不會連接到會議，因為它不會提供加入會議的確認。</span><span class="sxs-lookup"><span data-stu-id="89d28-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="89d28-108">啟用此功能時，收到撥出或撥打給我電話的人必須在傳統或行動電話上按 1 來確認他們想要加入會議。</span><span class="sxs-lookup"><span data-stu-id="89d28-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="89d28-109">若要為貴組織的所有會議啟用此功能，請設定 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數為 ```true``` 。</span><span class="sxs-lookup"><span data-stu-id="89d28-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="89d28-110">若要這麼做，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="89d28-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="89d28-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="89d28-111">Related topics</span></span>

- [<span data-ttu-id="89d28-112">為您的使用者設定語音來電功能</span><span class="sxs-lookup"><span data-stu-id="89d28-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="89d28-113">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="89d28-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)