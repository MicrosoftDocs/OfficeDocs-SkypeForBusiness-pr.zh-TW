---
title: 新增常設聊天室檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。 您可以使用檔案存放區現有的檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: 76169673848d9cbace41642d5058bfb60e90508a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218674"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="1a6fe-104">新增常設聊天室檔案存放區</span><span class="sxs-lookup"><span data-stu-id="1a6fe-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="1a6fe-105">您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-105">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="1a6fe-106">您可以使用檔案存放區現有的檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-106">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1a6fe-107">商務用 Skype Server 的檔案共用不能位於 Enterprise Edition 前端伺服器，但可以位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1a6fe-108">您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1a6fe-109">當您將 Persistent Chat Server 或 Persistent Chat Server 集區新增至您的拓撲時，拓撲產生器必須能夠設定檔案存放區，並設定檔案存放區 (Dacl) 上的自由存取控制清單，以用於檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="1a6fe-110">這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="1a6fe-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1a6fe-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="1a6fe-111">See also</span></span>

[<span data-ttu-id="1a6fe-112">在商務用 Skype Server 2015 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="1a6fe-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1a6fe-113">將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲</span><span class="sxs-lookup"><span data-stu-id="1a6fe-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="1a6fe-114">商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="1a6fe-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="1a6fe-115">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="1a6fe-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="1a6fe-116">商務用 Skype Server 2015 的拓撲基礎</span><span class="sxs-lookup"><span data-stu-id="1a6fe-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
