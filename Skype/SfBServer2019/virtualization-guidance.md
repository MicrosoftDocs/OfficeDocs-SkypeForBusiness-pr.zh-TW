---
title: '商務用 Skype Server 2019 的虛擬化支援 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：瞭解商務用 Skype Server 2019 的虛擬化支援。
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565952"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="c762d-103">商務用 Skype Server 2019 的虛擬化支援</span><span class="sxs-lookup"><span data-stu-id="c762d-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="c762d-104">虛擬化支援商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="c762d-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="c762d-105">支援虛擬化時，需要記住一些要點：</span><span class="sxs-lookup"><span data-stu-id="c762d-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="c762d-106">維護虛擬 CPU 與實體 CPU 的1:1 比率。</span><span class="sxs-lookup"><span data-stu-id="c762d-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="c762d-107">請勿移動來賓伺服器的運作方式。</span><span class="sxs-lookup"><span data-stu-id="c762d-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="c762d-108">不支援即時系統和虛擬機器的便攜性遷移。</span><span class="sxs-lookup"><span data-stu-id="c762d-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="c762d-109">停用所有主機上的超執行緒。</span><span class="sxs-lookup"><span data-stu-id="c762d-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="c762d-110">請勿在主伺服器上設定動態記憶體。</span><span class="sxs-lookup"><span data-stu-id="c762d-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="c762d-111">使用固定磁片或傳遞磁片（而非動態磁碟）。</span><span class="sxs-lookup"><span data-stu-id="c762d-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="c762d-112">針對虛擬來賓所需的虛擬機器監控程式，允許超過6-10% 的負載。</span><span class="sxs-lookup"><span data-stu-id="c762d-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="c762d-113">支援的虛擬機器監控程式</span><span class="sxs-lookup"><span data-stu-id="c762d-113">Supported hypervisors</span></span>

<span data-ttu-id="c762d-114">Windows Server 2016 和 Windows Server 2019 支援 SfB Server 2019。</span><span class="sxs-lookup"><span data-stu-id="c762d-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="c762d-115">針對協力廠商虛擬機器管理器，您需要已超過伺服器虛擬化驗證方案（SVVP）測試（適用于相關作業系統）的虛擬機器監控程式。</span><span class="sxs-lookup"><span data-stu-id="c762d-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="c762d-116">請參閱 SVVP 清單中的[Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25)。</span><span class="sxs-lookup"><span data-stu-id="c762d-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="c762d-117">請參閱 SVVP 清單中的[Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25)。</span><span class="sxs-lookup"><span data-stu-id="c762d-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
