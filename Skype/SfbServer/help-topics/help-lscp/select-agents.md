---
title: 選取代理程式
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
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: 代理人是指指派應答回應群組通話的使用者。 回應群組必須有指派的代理人群組，用以識別可以接收回應群組通話的代理人。 建立代理人群組的一種方法是，透過選取合格的使用者來定義自訂群組。 合格的使用者啟用商務用 Skype Server 和 Enterprise Voice。
ms.openlocfilehash: c245ea9816d60fc8448eeeb00bdfc8351e345784
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107999"
---
# <a name="select-agents"></a><span data-ttu-id="5602e-106">選取代理程式</span><span class="sxs-lookup"><span data-stu-id="5602e-106">Select Agents</span></span>

<span data-ttu-id="5602e-107">代理人是指指派應答回應群組通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="5602e-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="5602e-108">回應群組必須有指派的代理人群組，用以識別可以接收回應群組通話的代理人。</span><span class="sxs-lookup"><span data-stu-id="5602e-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="5602e-109">建立代理人群組的一種方法是，透過選取合格的使用者來定義自訂群組。</span><span class="sxs-lookup"><span data-stu-id="5602e-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="5602e-110">合格的使用者啟用商務用 Skype Server 和 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="5602e-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="5602e-111">您可以使用 [ **選取代理** ] 對話方塊，選取要新增至代理人群組的使用者。</span><span class="sxs-lookup"><span data-stu-id="5602e-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5602e-112">UI 參考</span><span class="sxs-lookup"><span data-stu-id="5602e-112">UI Reference</span></span>

<span data-ttu-id="5602e-113">下列清單說明 [ **選取代理** ] 對話方塊中的控制項。</span><span class="sxs-lookup"><span data-stu-id="5602e-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="5602e-114">**尋找** 搜尋使用者的 SIP 位址或顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="5602e-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="5602e-115">輸入全部或部分的位址或名稱。</span><span class="sxs-lookup"><span data-stu-id="5602e-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="5602e-116">保留搜尋方塊為空白，以顯示所有已啟用商務用 Skype Server 和 Enterprise Voice 的使用者。</span><span class="sxs-lookup"><span data-stu-id="5602e-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="5602e-117">**顯示的使用者上限** 變更顯示的傳回結果數目。</span><span class="sxs-lookup"><span data-stu-id="5602e-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="5602e-118">如果您期望許多結果，請使用此計數器來限制搜尋。</span><span class="sxs-lookup"><span data-stu-id="5602e-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="5602e-119">下列清單說明 [ **選取代理** ] 對話方塊中的欄位。</span><span class="sxs-lookup"><span data-stu-id="5602e-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="5602e-120">**代理程式** 顯示搜尋傳回的使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="5602e-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="5602e-121">**SIP 位址** 顯示搜尋傳回的使用者 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5602e-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="5602e-122">**電話語音** 顯示為使用者定義之 **電話語音** 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="5602e-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="5602e-123">**已啟用** 顯示針對使用者所定義之 [ **已啟用的 Lync Server** ] 欄位的值。</span><span class="sxs-lookup"><span data-stu-id="5602e-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="5602e-124">如需使用代理群組的詳細資訊，請參閱作業文件中的＜[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)＞。</span><span class="sxs-lookup"><span data-stu-id="5602e-124">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>