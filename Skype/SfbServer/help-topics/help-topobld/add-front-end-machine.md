---
title: 新增前端機器
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定您要在此集區中，新增為前端伺服器之每台電腦的完整網域名稱 (FQDN)。將電腦新增至清單後，您可以在發行拓撲之前，隨時更新電腦的 FQDN，或將它從集區移除。發行拓撲之後，要變更 FQDN 便需要在拓撲產生器中刪除伺服器，然後用新的 FQDN 將新的伺服器新增到集區。如需新增前端集區至拓撲的詳細資料，請參閱部署文件中的定義及設定前端集區。
---

# <a name="add-front-end-machine"></a>新增前端機器

指定您要在此集區中，新增為前端伺服器之每台電腦的完整網域名稱 (FQDN)。將電腦新增至清單後，您可以在發行拓撲之前，隨時更新電腦的 FQDN，或將它從集區移除。發行拓撲之後，要變更 FQDN 便需要在拓撲產生器中刪除伺服器，然後用新的 FQDN 將新的伺服器新增到集區。如需新增前端集區至拓撲的詳細資料，請參閱部署文件中的[定義及設定前端集區](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)。

> [!IMPORTANT]
> 請注意，拓撲產生器表示您最多可在集區中有20部前端伺服器。 支援的伺服器數目上限為12。 您最多可以有20個 statefull 伺服器定義在 fabric 中，其中12個可在任何時間使用中和線上。