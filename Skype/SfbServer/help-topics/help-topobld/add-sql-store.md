---
title: 新增 SQL 存放區
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 若要定義新的 SQL 儲存區，這表示您指定的是 SQL Server 型資料庫和 SQL Server 實例（預設實例或命名實例），您必須指定下列各項。
ms.openlocfilehash: 367d0bb57d673bdb062b5a1f99ead7cb426995c6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844506"
---
# <a name="add-sql-store"></a>新增 SQL 存放區

若要定義新的 SQL 儲存區，這表示您指定的是 SQL Server 型資料庫和 SQL Server 實例（預設實例或命名實例），您必須指定下列各項。

指定將主控您所定義之資料庫實例之 SQL Server 的完整功能變數名稱 (FQDN) 。

指定將主控資料的 SQL Server 實例。 您可以指定預設實例，也可以指定命名實例。

組合在特定實例中的資料庫，應明確瞭解。 如需伺服器組合及資料庫實例組合的詳細資訊，請參閱[Standard Edition server 部署](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)中前端集區部署和伺服器組合中[的伺服器組合](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)。