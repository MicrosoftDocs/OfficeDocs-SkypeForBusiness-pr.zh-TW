---
title: 新增前端關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 現在，您可以將伺服器角色與前端集區產生關聯，對需要部署其他伺服器的特定功能啟用支援。 您也可以稍後將伺服器角色與前端集區產生關聯。 可與前端集區相關聯的伺服器角色包括下列各項：
ms.openlocfilehash: df7183915316f4b3b7c198c5fce735fa6969e6057b7a0ef95a7ce12b74eb5b8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345750"
---
# <a name="add-front-end-associations"></a>新增前端關聯

現在，您可以將伺服器角色與前端集區產生關聯，對需要部署其他伺服器的特定功能啟用支援。 您也可以稍後將伺服器角色與前端集區產生關聯。 可與前端集區相關聯的伺服器角色包括下列各項：

- A/V Edge Server。 如需有關執行 A/V Edge Server 的詳細資訊，請參閱規劃檔中的 [規劃會議](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) 。

> [!IMPORTANT]
> 如果您現在啟用上述任一功能的支援，您發佈的拓撲設計將會包含實施每個選取功能所需的伺服器元件。 若要將拓撲發行成功，但沒有錯誤，您必須將實體電腦加入網域。 例如，如果您現在啟用封存支援，則必須先部署封存伺服器並設定適當的封存選項，才能開始封存組織的通訊。