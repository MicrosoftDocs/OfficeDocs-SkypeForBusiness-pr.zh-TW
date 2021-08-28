---
title: 新增 SQL 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定義新的 SQL 儲存區，這表示您指定的是 SQL Server 型資料庫和 SQL Server 實例（預設實例或命名實例），您必須指定下列各項。
ms.openlocfilehash: a20784ca216d8a1776605089a18e79a6d6f0f3c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597107"
---
# <a name="add-sql-store"></a>新增 SQL 存放區

若要定義新的 SQL 儲存區，這表示您指定的是 SQL Server 型資料庫和 SQL Server 實例（預設實例或命名實例），您必須指定下列各項。

指定將主控您所定義之資料庫實例之 SQL Server 的完整功能變數名稱 (FQDN) 。

指定將主控資料的 SQL Server 實例。 您可以指定預設實例，也可以指定命名實例。

組合在特定實例中的資料庫，應明確瞭解。 如需伺服器組合及資料庫實例組合的詳細資訊，請參閱[Standard Edition server 部署](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)中前端集區部署和伺服器組合中[的伺服器組合](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)。