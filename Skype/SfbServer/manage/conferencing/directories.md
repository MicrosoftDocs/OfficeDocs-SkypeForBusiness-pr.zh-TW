---
title: 在商務用 Skype Server 中建立會議目錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: '摘要: 瞭解如何在商務用 Skype Server 中建立會議目錄。'
ms.openlocfilehash: d2962e7e01ba5bb73ce82de9b5c0ff85550fbe99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193823"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="0cabb-103">在商務用 Skype Server 中建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="0cabb-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="0cabb-104">**摘要:** 瞭解如何在商務用 Skype Server 中建立會議目錄。</span><span class="sxs-lookup"><span data-stu-id="0cabb-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="0cabb-105">在使用商務用 Skype 時, 會議目錄會在參與者用來加入會議的字母數位會議 ID 之間保留對應, 以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。</span><span class="sxs-lookup"><span data-stu-id="0cabb-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="0cabb-106">建立會議目錄</span><span class="sxs-lookup"><span data-stu-id="0cabb-106">Create a conference directory</span></span>

<span data-ttu-id="0cabb-107">建立多個會議目錄可確保會議 Id 保持不變, 直到建立大量的會議為止。</span><span class="sxs-lookup"><span data-stu-id="0cabb-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="0cabb-108">在每位使用者有典型會議數的組織中, 我們建議您為池中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="0cabb-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="0cabb-109">使用這種準則, 會議 Id 通常可以保持很小的狀態。</span><span class="sxs-lookup"><span data-stu-id="0cabb-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="0cabb-110">不過, 一旦會議目錄數量 (跨多個池) 超過9個, 會議 ID 長度就會增長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="0cabb-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="0cabb-111">會議 ID 的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="0cabb-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="0cabb-112">若要建立會議目錄, 請使用**CsConferenceDirectory** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0cabb-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="0cabb-113">例如, 下列命令會建立一個在 pool atl-cs-001.litwareinc.com 上託管的身分識別42的會議目錄:</span><span class="sxs-lookup"><span data-stu-id="0cabb-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="0cabb-114">如需詳細資訊, 請參閱[新 CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0cabb-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  

