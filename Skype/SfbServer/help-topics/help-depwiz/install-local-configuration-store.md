---
title: 安裝本機組態存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要開始安裝新的商務用 Skype Server 2015 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。 本機設定存放區將充當商務用 Skype Server 中央管理存放區的唯讀複本 (CMS) 。 您必須以電腦的本機系統管理員身分登入您執行 [安裝本機設定存放區] 步驟的伺服器，且擁有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。 如果您在 Edge Server 上執行安裝程式，則您不必是 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員。 拓撲產生器定義檔會從匯出的定義檔讀取，而不是從中央管理存放區讀取。 若要匯出拓撲產生器定義檔，並將其提供給 Edge Server，請參閱匯出拓撲及將其複製到 Edge 安裝的外部媒體主題。
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827143"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="18538-108">安裝本機組態存放區</span><span class="sxs-lookup"><span data-stu-id="18538-108">Install Local Configuration Store</span></span>

<span data-ttu-id="18538-109">若要開始安裝新的商務用 Skype Server 2015 角色服務器，您必須先安裝將主控本機設定存放區的本機 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="18538-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="18538-110">本機設定存放區將充當商務用 Skype Server 中央管理存放區的唯讀複本 (CMS) 。</span><span class="sxs-lookup"><span data-stu-id="18538-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="18538-111">您必須以電腦的本機系統管理員身分登入您執行 **[安裝本機設定存放區]** 步驟的伺服器，且擁有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="18538-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="18538-112">如果您在 Edge Server 上執行安裝程式，則您不必是 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="18538-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="18538-113">拓撲產生器定義檔會從匯出的定義檔讀取，而不是從中央管理存放區讀取。</span><span class="sxs-lookup"><span data-stu-id="18538-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="18538-114">若要匯出拓撲產生器定義檔，並將其提供給 Edge Server，請參閱 [匯出拓撲及將其複製到 Edge 安裝的外部媒體](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)主題。</span><span class="sxs-lookup"><span data-stu-id="18538-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="18538-115">若要開始安裝：</span><span class="sxs-lookup"><span data-stu-id="18538-115">To begin the installation:</span></span>

1. <span data-ttu-id="18538-116">在 [商務用 Skype Server 2015] 頁面上，按一下 [ **步驟1：安裝本機設定存放區**] 旁邊的 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="18538-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="18538-117">在 [ **本機伺服器** 設定] 頁面上，確定已選取 [ **自動從中央管理存放區取得** 設定] 選項，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="18538-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="18538-118">當本機伺服器設定安裝完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="18538-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="18538-119">安裝本機 SQL Server 可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="18538-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="18538-120">安裝 SQL Server 時，將不會在安裝摘要畫面上看到進行中的更新。</span><span class="sxs-lookup"><span data-stu-id="18538-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="18538-121">如果您想要監視安裝進度，請使用 [工作管理員] 來觀賞 SQL Server 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="18538-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


