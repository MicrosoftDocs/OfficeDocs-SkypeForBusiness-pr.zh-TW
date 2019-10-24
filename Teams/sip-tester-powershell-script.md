---
title: 測試直接路由會話邊界控制器連線的 PowerShell 腳本
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本範例來測試 Microsoft 團隊中的直接路由會話框線控制器連線。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639314"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="03a64-103">測試直接路由會話邊界控制器連線的 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="03a64-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="03a64-104">SIP 測試者用戶端是一個範例 PowerShell 腳本，您可以用來測試 Microsoft 團隊中的直接路由會話邊界控制器（SBC）連線。</span><span class="sxs-lookup"><span data-stu-id="03a64-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="03a64-105">此腳本會利用直接路由來測試客戶配對會話初始通訊協定（SIP）幹線的基本功能。</span><span class="sxs-lookup"><span data-stu-id="03a64-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="03a64-106">此腳本會將 SIP 測試提交至測試回合程式，等待結果，然後以易於閱讀的格式呈現。</span><span class="sxs-lookup"><span data-stu-id="03a64-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="03a64-107">您可以使用此腳本來測試下列案例：</span><span class="sxs-lookup"><span data-stu-id="03a64-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="03a64-108">輸出和撥出通話</span><span class="sxs-lookup"><span data-stu-id="03a64-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="03a64-109">同時撥打</span><span class="sxs-lookup"><span data-stu-id="03a64-109">Simultaneous ring</span></span>
- <span data-ttu-id="03a64-110">媒體升級</span><span class="sxs-lookup"><span data-stu-id="03a64-110">Media escalation</span></span>
- <span data-ttu-id="03a64-111">顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="03a64-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="03a64-112">下載腳本與檔</span><span class="sxs-lookup"><span data-stu-id="03a64-112">Download the script and documentation</span></span>

<span data-ttu-id="03a64-113">下載[SIP 測試程式用戶端腳本及檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="03a64-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>