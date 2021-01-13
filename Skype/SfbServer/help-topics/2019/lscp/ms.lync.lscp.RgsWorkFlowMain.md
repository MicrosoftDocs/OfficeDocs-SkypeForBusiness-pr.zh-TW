---
title: 回應群組工作流程
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: 回應群組中包含代理群組、佇列及工作流程。 回應群組工作流程定義回應群組應用程式接聽電話時所採取的動作。
ms.openlocfilehash: b4f9a80be55e00d5874c79cf426e331a464d0e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820263"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="3d8c7-104">回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="3d8c7-104">Response Groups Workflow</span></span>

<span data-ttu-id="3d8c7-105">回應群組中包含代理群組、佇列及工作流程。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="3d8c7-106">回應群組工作流程定義回應群組應用程式接聽電話時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="3d8c7-107">[**回應群組**  -  **工作流程**] 頁面會顯示為組織定義的所有回應群組工作流程清單。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3d8c7-108">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="3d8c7-108">Tasks you can perform</span></span>

<span data-ttu-id="3d8c7-109">您可以從「**回應群組**  -  **工作流程**」頁面執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="3d8c7-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="3d8c7-110">建立或變更群組搜尋工作流程</span><span class="sxs-lookup"><span data-stu-id="3d8c7-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="3d8c7-111">建立或變更互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="3d8c7-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3d8c7-112">UI 參考</span><span class="sxs-lookup"><span data-stu-id="3d8c7-112">UI Reference</span></span>

<span data-ttu-id="3d8c7-113">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="3d8c7-114">**建立或編輯工作流程** 開啟 [回應群組] 設定工具，以建立或編輯工作流程。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="3d8c7-115">**Refresh** 重新整理工作流程清單。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="3d8c7-116">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3d8c7-117">**名稱** 指派給工作流程的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="3d8c7-118">**服務** 主控工作流程的 **ApplicationServer** 服務。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="3d8c7-119">**SIP 位址** 將接聽工作流程通話之群組的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="3d8c7-120">**電話** 呼叫以送達此回應群組的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="3d8c7-121">**語言** 用於語音辨識及文字轉換語音的語言。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="3d8c7-122">**IVR** 會指出工作流程是否為群組搜尋或互動式工作流程。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="3d8c7-123">**已啟用** 會指出是否要啟用工作流程以接收來電。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="3d8c7-124">如需有關回應群組功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype Server 中規劃回應群組應用程式](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="3d8c7-125">如需使用回應群組工作流程的詳細資訊，請參閱 Operations 檔中的 [管理回應群組工作流程](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3d8c7-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


