---
title: 安裝本機設定存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要開始安裝新的商務用 Skype Server 2015 角色服務器, 您必須先安裝將裝載本機配置存放區的本機 SQL 伺服器。 本機配置存儲將充當商務用 Skype Server 中央管理商店 (CMS) 的唯讀複本。 您必須以電腦的本機系統管理員身分登入伺服器 (您在伺服器上執行「安裝本機設定存放區」步驟)，並具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 若要在 Edge Server 上執行安裝程式，便無需具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 會從匯出的定義檔 (而不是從中央管理儲存體) 讀取拓撲建立器定義檔。 若要匯出拓撲建立器定義檔, 並將它提供給邊緣伺服器, 請參閱匯出拓撲並將它複製到外部媒體以進行 Edge 安裝的主題。
ms.openlocfilehash: c3da29e6c9630b22e7ae947f9b23ab5dbeebd13c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193296"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="7285f-108">安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="7285f-108">Install Local Configuration Store</span></span>

<span data-ttu-id="7285f-109">若要開始安裝新的商務用 Skype Server 2015 角色服務器, 您必須先安裝將裝載本機配置存放區的本機 SQL 伺服器。</span><span class="sxs-lookup"><span data-stu-id="7285f-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="7285f-110">本機配置存儲將充當商務用 Skype Server 中央管理商店 (CMS) 的唯讀複本。</span><span class="sxs-lookup"><span data-stu-id="7285f-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="7285f-111">您必須以電腦的本機系統管理員身分登入伺服器 (您在伺服器上執行「安裝本機設定存放區」步驟)\*\*\*\*，並具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="7285f-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7285f-112">若要在 Edge Server 上執行安裝程式，便無需具備 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="7285f-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7285f-113">會從匯出的定義檔 (而不是從中央管理儲存體) 讀取拓撲建立器定義檔。</span><span class="sxs-lookup"><span data-stu-id="7285f-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="7285f-114">若要匯出拓撲建立器定義檔, 並將它提供給邊緣伺服器, 請參閱[匯出拓撲並將它複製到外部媒體以進行 Edge 安裝](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)的主題。</span><span class="sxs-lookup"><span data-stu-id="7285f-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="7285f-115">若要開始安裝：</span><span class="sxs-lookup"><span data-stu-id="7285f-115">To begin the installation:</span></span>

1. <span data-ttu-id="7285f-116">在商務用 Skype Server 2015 頁面上, 按一下 [ **Step1: 安裝本機配置存放區**] 旁的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="7285f-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="7285f-117">在「本機伺服器設定」\*\*\*\* 頁面上，確定已選取 [自動從中央管理存放區擷取設定]\*\*\*\* 選項，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7285f-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="7285f-118">當本機伺服器設定安裝完成時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7285f-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="7285f-119">安裝本機 SQL Server 可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="7285f-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="7285f-120">在安裝 SQL Server 時, 您將不會在安裝摘要畫面上看到所進行的更新。</span><span class="sxs-lookup"><span data-stu-id="7285f-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="7285f-121">如果您想要監視安裝進度, 請使用 [工作管理員] 來觀察 SQL Server 設定。</span><span class="sxs-lookup"><span data-stu-id="7285f-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


