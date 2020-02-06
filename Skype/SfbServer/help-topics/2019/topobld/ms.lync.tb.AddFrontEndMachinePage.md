---
title: 新增前端機器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 指定您想要在此池中新增為前端伺服器的每個電腦的完整功能變數名稱（FQDN）。 將電腦新增至清單後，即可更新電腦的 FQDN，或在發行拓撲前，隨時將它從集區中移除。 發佈拓撲之後，變更 FQDN 需要先刪除拓撲建立器中的伺服器，然後使用新的 FQDN 將新的伺服器新增到該池。 如需將 [前端] 池新增到拓撲中的詳細資料，請參閱在部署檔中定義及設定前端池。
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798540"
---
# <a name="add-front-end-machine"></a>新增前端機器

指定您想要在此池中新增為前端伺服器的每個電腦的完整功能變數名稱（FQDN）。 將電腦新增至清單後，即可更新電腦的 FQDN，或在發行拓撲前，隨時將它從集區中移除。 發佈拓撲之後，變更 FQDN 需要先刪除拓撲建立器中的伺服器，然後使用新的 FQDN 將新的伺服器新增到該池。 如需將 [前端] 池新增到拓撲中的詳細資料，請參閱在部署檔中[定義及設定前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。

> [!IMPORTANT]
> 請注意，拓撲建立器表示您最多可以在一個池中擁有20個前端伺服器。 支援的伺服器數目上限為12個。 您最多可以在結構中定義20個 statefull 伺服器，其中12個可在任何時間使用中且在線上。


