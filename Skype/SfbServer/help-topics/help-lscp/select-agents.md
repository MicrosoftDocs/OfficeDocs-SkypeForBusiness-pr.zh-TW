---
title: 選取代理人
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: '[代理程式] 是指派給回應群組通話的使用者。 回應群組必須獲派一個代理人群組，識別要接聽回應群組電話的代理人。 建立代理人群組的方法之一，是藉由選取符合資格的使用者來定義自訂群組。 已啟用適用于商務用 Skype Server 和企業語音的合格使用者。'
ms.openlocfilehash: 2950295bcf78ee2c7c904375d009a8fba085b85f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822306"
---
# <a name="select-agents"></a><span data-ttu-id="4c3f1-106">選取代理人</span><span class="sxs-lookup"><span data-stu-id="4c3f1-106">Select Agents</span></span>

<span data-ttu-id="4c3f1-107">[代理程式] 是指派給回應群組通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="4c3f1-108">回應群組必須獲派一個代理人群組，識別要接聽回應群組電話的代理人。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="4c3f1-109">建立代理人群組的方法之一，是藉由選取符合資格的使用者來定義自訂群組。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="4c3f1-110">已啟用適用于商務用 Skype Server 和企業語音的合格使用者。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="4c3f1-111">您可以使用 [選取代理人]\*\*\*\* 對話方塊，選取要新增至代理人群組的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4c3f1-112">UI 參考</span><span class="sxs-lookup"><span data-stu-id="4c3f1-112">UI Reference</span></span>

<span data-ttu-id="4c3f1-113">下列清單說明 [選取代理人]\*\*\*\* 對話方塊中的控制項。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="4c3f1-114">**尋找**搜尋使用者的 SIP 位址或顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="4c3f1-115">輸入全部或部分的位址或名稱。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="4c3f1-116">[搜尋] 方塊保持空白，以顯示所有已啟用商務用 Skype Server 和企業語音的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="4c3f1-117">**要顯示的使用者數目上限**變更顯示的傳回結果數。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="4c3f1-118">如果您預計有許多結果，請使用這個計數器來限制搜尋。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="4c3f1-119">下列清單說明 [選取代理人]\*\*\*\* 對話方塊中的欄位。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="4c3f1-120">**代理程式**顯示搜尋所傳回的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="4c3f1-121">**SIP 位址**顯示搜尋所傳回的使用者 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="4c3f1-122">**電話**顯示為使用者定義的**電話**功能欄位的值。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="4c3f1-123">**已啟用**顯示為使用者定義的 [**已啟用的 Lync Server** ] 欄位值。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="4c3f1-124">如需管理代理人群組的詳細資訊，請參閱作業文件中的〈[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="4c3f1-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


