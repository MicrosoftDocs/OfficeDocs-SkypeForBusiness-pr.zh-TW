---
title: 移轉類比裝置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype 伺服器提供類比裝置的支援。 具體說來，支援的類比裝置是類比音訊電話和類比傳真電腦。 您可以設定合格的閘道，以支援在商務用 Skype Server 環境中使用類比裝置。 在您遷移到商務用 Skype Server 2019 之後，您也必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server Management 命令介面，先檢索與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移到商務用 Skype Server 2019 池。
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813591"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="f2f7e-107">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="f2f7e-107">Migrate analog devices</span></span>

<span data-ttu-id="f2f7e-108">商務用 Skype 伺服器提供類比裝置的支援。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="f2f7e-109">具體說來，支援的類比裝置是類比音訊電話和類比傳真電腦。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="f2f7e-110">您可以設定合格的閘道，以支援在商務用 Skype Server 環境中使用類比裝置。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="f2f7e-111">在您遷移到商務用 Skype Server 2019 之後，您也必須遷移與類比裝置相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="f2f7e-112">使用商務用 Skype Server Management 命令介面，先檢索與舊版類比裝置相關聯的所有連絡人物件，然後將這些物件移到商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="f2f7e-113">遷移類比裝置</span><span class="sxs-lookup"><span data-stu-id="f2f7e-113">To migrate analog devices</span></span>

1. <span data-ttu-id="f2f7e-114">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f2f7e-115">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="f2f7e-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="f2f7e-116">確認所有連絡人物件都已移至商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f2f7e-117">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="f2f7e-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="f2f7e-118">確認所有連絡人物件現在都與商務用 Skype Server 2019 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="f2f7e-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


