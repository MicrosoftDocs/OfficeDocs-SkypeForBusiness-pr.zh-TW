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
description: 在商務用 Skype Online 中使用 PowerShell 管理 Exchange 整合通訊功能，例如自動語音應答及訂閱者存取及託管語音信箱。
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692678"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="e69bf-103">管理 Exchange 整合通訊與託管語音信箱</span><span class="sxs-lookup"><span data-stu-id="e69bf-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="e69bf-104">您可以使用一組 Cmdlet，在商務用 Skype Online 中管理 Exchange 整合訊息及託管語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e69bf-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="e69bf-105">管理 Exchange 整合訊息及託管語音信箱</span><span class="sxs-lookup"><span data-stu-id="e69bf-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="e69bf-106">下列 Cmdlet 可用來管理 Exchange 整合通訊（UM）及託管的語音信箱原則：</span><span class="sxs-lookup"><span data-stu-id="e69bf-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  

| <span data-ttu-id="e69bf-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e69bf-107">**Cmdlet**</span></span>                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="e69bf-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="e69bf-108">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [<span data-ttu-id="e69bf-109">CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="e69bf-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="e69bf-110">新-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="e69bf-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="e69bf-111">移除-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="e69bf-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="e69bf-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="e69bf-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | <span data-ttu-id="e69bf-113">如果 Exchange UM 是託管服務，就會建立並管理用於自動語音應答及訂閱者存取服務的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e69bf-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="e69bf-114">商務用 Skype Online 可與 Exchange UM 搭配使用，以提供多種語音相關功能，包括自動助理及訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="e69bf-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="e69bf-115">自動語音應答提供通話自動接聽的方式，並路由至正確的人員。</span><span class="sxs-lookup"><span data-stu-id="e69bf-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="e69bf-116">[訂閱者存取] 可讓使用者連線到 Exchange UM 並檢索電子郵件、語音訊息、連絡人和行事曆資訊。</span><span class="sxs-lookup"><span data-stu-id="e69bf-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="e69bf-117">當 Exchange UM 是作為託管服務提供時，必須使用 Microsoft PowerShell 來建立用於自動語音應答和訂閱者存取服務的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e69bf-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="e69bf-118">這些物件是使用**CsExUmContact** Cmdlet 來建立和管理。</span><span class="sxs-lookup"><span data-stu-id="e69bf-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
| [<span data-ttu-id="e69bf-119">CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e69bf-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="e69bf-120">授與 CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="e69bf-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | <span data-ttu-id="e69bf-121">管理組織中使用的託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="e69bf-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="e69bf-122">託管的語音信箱原則可指定未應答的呼叫路由至 Exchange UM 服務的方式。</span><span class="sxs-lookup"><span data-stu-id="e69bf-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="e69bf-123">這些原則只會影響已針對 Exchange UM 託管語音信箱啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="e69bf-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="e69bf-124">若要確認使用者是否已啟用託管的語音信箱，請從 PowerShell 提示執行類似下列的命令。</span><span class="sxs-lookup"><span data-stu-id="e69bf-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="e69bf-125">\`CsOnlineUser-身分識別 "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="e69bf-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span>                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a><span data-ttu-id="e69bf-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="e69bf-126">Related topics</span></span>
[<span data-ttu-id="e69bf-127">使用 Windows PowerShell 設定商務用 skype online 管理電腦</span><span class="sxs-lookup"><span data-stu-id="e69bf-127">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
