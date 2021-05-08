---
title: 管理 Exchange 整合通訊與託管語音信箱
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 PowerShell 在 Exchange管理統一訊息功能，例如自動語音信箱和訂閱者存取，以及 商務用 Skype語音信箱。
ms.openlocfilehash: 1a841b377fbc84d85f085dc9d479fa05cc0b2be4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238736"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="6bdd4-103">管理 Exchange 整合通訊與託管語音信箱</span><span class="sxs-lookup"><span data-stu-id="6bdd4-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6bdd4-104">您可以使用一Exchange Cmdlet 在 商務用 Skype Online 中管理統一訊息和主商務用 Skype語音信箱。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="6bdd4-105">管理Exchange郵件和託管語音信箱</span><span class="sxs-lookup"><span data-stu-id="6bdd4-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="6bdd4-106">下列 Cmdlet 可用來管理 UM Exchange和託管語音信箱 (統一) 訊息：</span><span class="sxs-lookup"><span data-stu-id="6bdd4-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  

| <span data-ttu-id="6bdd4-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6bdd4-107">**Cmdlet**</span></span>                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="6bdd4-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="6bdd4-108">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="6bdd4-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6bdd4-109">Get-CsExUmContact</span></span>](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [<span data-ttu-id="6bdd4-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6bdd4-110">New-CsExUmContact</span></span>](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[<span data-ttu-id="6bdd4-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6bdd4-111">Remove-CsExUmContact</span></span>](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[<span data-ttu-id="6bdd4-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="6bdd4-112">Set-CsExUmContact</span></span>](/powershell/module/skype/Set-CsExUmContact) <br/> | <span data-ttu-id="6bdd4-113">建立及管理用於自動總機和訂閱者 Access 服務的連絡人物件，Exchange UM 是託管服務時。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="6bdd4-114">商務用 SkypeOnline 可Exchange UM，提供數種語音相關功能，包括自動語音助理和訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="6bdd4-115">自動回應提供自動接聽電話的方式，並路由給正確的人員。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="6bdd4-116">訂閱者 Access 可讓使用者Exchange UM，並取得電子郵件、語音留言、連絡人和日曆資訊。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="6bdd4-117">當 Exchange UM 作為託管服務提供時，用於自動助理和訂閱者 Access 服務的連絡人物件必須使用 Microsoft PowerShell 建立。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="6bdd4-118">這些物件是使用 **CsExUmContact** Cmdlet 建立和管理。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
| [<span data-ttu-id="6bdd4-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6bdd4-119">Get-CSHostedVoicemailPolicy</span></span>](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[<span data-ttu-id="6bdd4-120">Grant-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="6bdd4-120">Grant-CSHostedVoicemailPolicy</span></span>](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | <span data-ttu-id="6bdd4-121">管理組織中所使用的託管語音信箱政策。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="6bdd4-122">託管語音信箱政策會指定未接聽的來電如何路由至Exchange UM 服務。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="6bdd4-123">這些策略只會影響已啟用 UM Exchange語音信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="6bdd4-124">若要驗證使用者是否已啟用託管語音信箱，請從 PowerShell 提示執行類似下列的命令。</span><span class="sxs-lookup"><span data-stu-id="6bdd4-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="6bdd4-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="6bdd4-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span>                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a><span data-ttu-id="6bdd4-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="6bdd4-126">Related topics</span></span>
[<span data-ttu-id="6bdd4-127">使用電腦設定商務用 skype 線上管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bdd4-127">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
