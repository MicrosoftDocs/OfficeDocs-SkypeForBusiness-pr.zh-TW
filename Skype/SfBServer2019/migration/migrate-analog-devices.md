---
title: 移轉類比裝置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype 伺服器提供類比裝置的支援。 具體而言，支援的類比裝置為類比語音電話與類比傳真機。 您可以設定合格的閘道，以支援在商務用 Skype 伺服器環境中使用類比裝置。 遷移至商務用 Skype Server 2019 之後，您還必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server 管理命令介面若要先取得與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752825"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="ab96b-107">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="ab96b-107">Migrate analog devices</span></span>

<span data-ttu-id="ab96b-108">商務用 Skype 伺服器提供類比裝置的支援。</span><span class="sxs-lookup"><span data-stu-id="ab96b-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="ab96b-109">具體而言，支援的類比裝置為類比語音電話與類比傳真機。</span><span class="sxs-lookup"><span data-stu-id="ab96b-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="ab96b-110">您可以設定合格的閘道，以支援在商務用 Skype 伺服器環境中使用類比裝置。</span><span class="sxs-lookup"><span data-stu-id="ab96b-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="ab96b-111">遷移至商務用 Skype Server 2019 之後，您還必須遷移與類比裝置相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="ab96b-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="ab96b-112">使用商務用 Skype Server 管理命令介面若要先取得與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移至商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="ab96b-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="ab96b-113">遷移類比裝置</span><span class="sxs-lookup"><span data-stu-id="ab96b-113">To migrate analog devices</span></span>

1. <span data-ttu-id="ab96b-114">啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ab96b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ab96b-115">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="ab96b-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="ab96b-116">確認已將所有連絡人物件移至商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="ab96b-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ab96b-117">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="ab96b-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="ab96b-118">確認所有連絡人物件現在已與商務用 Skype Server 2019 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="ab96b-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


