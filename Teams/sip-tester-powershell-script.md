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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116689"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="71ca3-103">測試直接路由會話邊界控制器連線的 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="71ca3-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="71ca3-104">SIP 測試者用戶端是一個範例 PowerShell 腳本，您可以用來測試 Microsoft 團隊中的直接路由會話邊界控制器（SBC）連線。</span><span class="sxs-lookup"><span data-stu-id="71ca3-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="71ca3-105">此腳本會利用直接路由來測試客戶配對會話初始通訊協定（SIP）幹線的基本功能。</span><span class="sxs-lookup"><span data-stu-id="71ca3-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="71ca3-106">此腳本會將 SIP 測試提交至測試回合程式，等待結果，然後以易於閱讀的格式呈現。</span><span class="sxs-lookup"><span data-stu-id="71ca3-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="71ca3-107">您可以使用此腳本來測試下列案例：</span><span class="sxs-lookup"><span data-stu-id="71ca3-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="71ca3-108">輸出和撥出通話</span><span class="sxs-lookup"><span data-stu-id="71ca3-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="71ca3-109">同時撥打</span><span class="sxs-lookup"><span data-stu-id="71ca3-109">Simultaneous ring</span></span>
- <span data-ttu-id="71ca3-110">媒體升級</span><span class="sxs-lookup"><span data-stu-id="71ca3-110">Media escalation</span></span>
- <span data-ttu-id="71ca3-111">顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="71ca3-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="71ca3-112">下載腳本與檔</span><span class="sxs-lookup"><span data-stu-id="71ca3-112">Download the script and documentation</span></span>

<span data-ttu-id="71ca3-113">下載[SIP 測試程式用戶端腳本及檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="71ca3-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="71ca3-114">SIP 測試用戶端腳本只支援 adal.ps 版本3.19.8.1。</span><span class="sxs-lookup"><span data-stu-id="71ca3-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="71ca3-115">如果使用的是更新版本的 adal.ps，就會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="71ca3-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
