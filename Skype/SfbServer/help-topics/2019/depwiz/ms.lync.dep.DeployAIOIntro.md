---
title: 準備單一 Standard Edition Server (簡介)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 若要開始安裝商務用 Skype Server Standard Edition server，該伺服器將保留中央管理存放區和您所選取的其他組合服務，您必須以要成為 Standard Edition server 之伺服器上的本機系統管理員群組成員的身分登入。 [準備單一 Standard Edition Server] 頁面詳述初始安裝的需求。 電腦必須是您要部署它所在之網域的成員，而且您必須已成功完成樹系的架構、樹系和網域準備工作。
ms.openlocfilehash: 08ea84c0d136339e782c32785c1c4fb536f877cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820623"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="98039-105">準備單一 Standard Edition Server (簡介)</span><span class="sxs-lookup"><span data-stu-id="98039-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="98039-106">若要開始安裝商務用 Skype Server Standard Edition server，該伺服器將保留中央管理存放區和您所選取的其他組合服務，您必須以要成為 Standard Edition server 之伺服器上的本機系統管理員群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="98039-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="98039-107">[ **準備單一 Standard Edition Server** ] 頁面詳述初始安裝的需求。</span><span class="sxs-lookup"><span data-stu-id="98039-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="98039-108">電腦必須是您要部署它所在之網域的成員，而且您必須已成功完成樹系的架構、樹系和網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="98039-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="98039-109">這項特定工作是用來設定 Standard Edition server 作為基礎結構中的第一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="98039-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="98039-110">此工作會將中央管理存放區（即 SQL Server Express）安裝到 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="98039-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="98039-111">如果您已經部署了其他 Standard Edition 伺服器或前端集區，則應該按一下 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="98039-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98039-112">完成此工作之後，如果尚未安裝拓撲產生器 (，請將其安裝) 並設定拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="98039-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="98039-113">您必須有可用的中央管理存放區（透過完成本主題所述的工作加以部署），才能發行拓撲檔。</span><span class="sxs-lookup"><span data-stu-id="98039-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

