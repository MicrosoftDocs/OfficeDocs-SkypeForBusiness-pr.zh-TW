---
title: 登錄器 SBA 設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 您編輯復原設定，並設定下列屬性：
ms.openlocfilehash: 7eb90efde862b6326ea6f43f27937751ebff0ce9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797244"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="88a18-103">登錄器 SBA 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="88a18-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="88a18-104">您編輯**復原**設定，並設定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="88a18-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="88a18-105">從清單中選取 [**關聯的使用者服務] 和 [備份註冊機構] 池**。</span><span class="sxs-lookup"><span data-stu-id="88a18-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="88a18-106">或者，選取 [**自動容錯移轉及語音容錯回復**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="88a18-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="88a18-107">設定**語音失敗偵測間隔（秒）** 和**語音回切間隔（秒）**。</span><span class="sxs-lookup"><span data-stu-id="88a18-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="88a18-108">根據預設，語音容錯回復的間隔是120秒，而語音回切則是240秒。</span><span class="sxs-lookup"><span data-stu-id="88a18-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="88a18-109">針對容錯移轉與回切間隔定義的秒數應該經過仔細的測試，以確保復原功能如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="88a18-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="88a18-110">將間隔設定為 [低] （即小於120秒），或容錯移轉與回切設定太接近，可能會導致實際的容錯移轉與回切無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="88a18-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="88a18-111">**確定**：接受並認可對話方塊的變更。</span><span class="sxs-lookup"><span data-stu-id="88a18-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="88a18-112">**取消**：捨棄變更，並關閉對話方塊。</span><span class="sxs-lookup"><span data-stu-id="88a18-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="88a18-113">**說明**：顯示此說明畫面。</span><span class="sxs-lookup"><span data-stu-id="88a18-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="88a18-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="88a18-114">See also</span></span>

[<span data-ttu-id="88a18-115">規劃企業語音復原</span><span class="sxs-lookup"><span data-stu-id="88a18-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
