---
title: 選取服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectPool
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6086162-8a41-4e75-afa3-7d1889ffdc90
description: 使用 [選取服務] 對話方塊，尋找您環境中可用的服務。 若要使用現有的服務，請按一下清單中的服務，然後按一下 [確定]。
ms.openlocfilehash: 06ee0217a8a495a881c9925c57e33311e4944607
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108039"
---
# <a name="select-a-service"></a>選取服務

使用 [ **選取服務** ] 對話方塊，尋找您環境中可用的服務。 若要使用現有的服務，請按一下清單中的服務，然後按一下 **[確定]**。

如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [ **選取服務** ] 頁面上執行下列工作：

- [設定類別](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [為聊天室設定增益集](/previous-versions/office/lync-server-2013/lync-server-2013-configure-add-ins-for-rooms)

- [以全域方式設定或針對常設聊天室伺服器集區設定常設聊天室伺服器選項](/previous-versions/office/lync-server-2013/lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool)

如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。

## <a name="to-configure-categories-for-chat-rooms"></a>設定聊天室的類別

在 [ **選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。 服務是 persistent chat Server 集區，Persistent Chat (用戶端) 使用它來識別類別所屬的集區。 類別只能隸屬于一部 Persistent Chat Server 集區，無法移至另一個集區，或與另一個集區共用。

## <a name="to-configure-add-ins-for-chat-rooms"></a>為聊天室設定增益集

在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>設定特定 Persistent Chat Server 集區的持續聊天選項

在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。

如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 。 如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in Operations 檔中。