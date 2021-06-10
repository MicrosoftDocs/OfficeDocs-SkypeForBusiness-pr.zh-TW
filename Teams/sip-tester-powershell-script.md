---
title: 測試直接路由會話邊界控制器連接的 PowerShell 腳本
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本範例來測試直接路由會話邊界控制器在 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834273"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="1bb68-103">測試直接路由會話邊界控制器連接的 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="1bb68-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="1bb68-104">SIP 測試程式用戶端是一個範例 PowerShell 腳本，可用於測試直接路由會話邊界控制器 (SBC) 連接Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1bb68-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="1bb68-105">此腳本會使用直接路由測試由客戶配對的會話初始通訊協定 (SIP) 主幹的基本功能。</span><span class="sxs-lookup"><span data-stu-id="1bb68-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="1bb68-106">腳本會提交 SIP 測試給測試執行者、等待結果，然後以可讀取的格式呈現。</span><span class="sxs-lookup"><span data-stu-id="1bb68-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="1bb68-107">您可以使用此腳本來測試下列案例：</span><span class="sxs-lookup"><span data-stu-id="1bb68-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="1bb68-108">外發和傳入通話</span><span class="sxs-lookup"><span data-stu-id="1bb68-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="1bb68-109">同時響鈴</span><span class="sxs-lookup"><span data-stu-id="1bb68-109">Simultaneous ring</span></span>
- <span data-ttu-id="1bb68-110">媒體升級</span><span class="sxs-lookup"><span data-stu-id="1bb68-110">Media escalation</span></span>
- <span data-ttu-id="1bb68-111">諮詢轉移</span><span class="sxs-lookup"><span data-stu-id="1bb68-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="1bb68-112">下載腳本和檔</span><span class="sxs-lookup"><span data-stu-id="1bb68-112">Download the script and documentation</span></span>

<span data-ttu-id="1bb68-113">下載 [SIP 測試程式用戶端腳本和檔](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="1bb68-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bb68-114">SIP 測試程式用戶端腳本僅 adal.ps 版本 3.19.8.1。</span><span class="sxs-lookup"><span data-stu-id="1bb68-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="1bb68-115">如果使用較新版本的版本，系統 adal.ps 錯誤。</span><span class="sxs-lookup"><span data-stu-id="1bb68-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
