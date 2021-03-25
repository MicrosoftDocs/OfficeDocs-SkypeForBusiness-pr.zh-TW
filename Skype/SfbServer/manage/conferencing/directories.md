---
title: 在商務用 Skype Server 中建立會議目錄
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議目錄。
ms.openlocfilehash: e4d73cc73a5c3c343e8a4734923cf80fb2590211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119472"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="a5b2d-103">在商務用 Skype Server 中建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="a5b2d-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="a5b2d-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立會議目錄。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5b2d-105">會議目錄會維護參與者在使用商務用 Skype 時加入會議時所用的字母數位會議識別碼之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="a5b2d-106">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="a5b2d-106">Create a conference directory</span></span>

<span data-ttu-id="a5b2d-107">建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="a5b2d-108">在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="a5b2d-109">使用這種指導方針，會議 IDs 一般會變小。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="a5b2d-110">不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼長度就會成長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="a5b2d-111">會議識別碼的格式如下：</span><span class="sxs-lookup"><span data-stu-id="a5b2d-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="a5b2d-112">若要建立會議目錄，請使用 **New-CsConferenceDirectory** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="a5b2d-113">例如，下列命令會建立「集區 atl-cs-001.litwareinc.com」42所主控的會議目錄，該目錄會主控于集區：</span><span class="sxs-lookup"><span data-stu-id="a5b2d-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="a5b2d-114">如需詳細資訊，請參閱 [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a5b2d-114">For more information, see [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
