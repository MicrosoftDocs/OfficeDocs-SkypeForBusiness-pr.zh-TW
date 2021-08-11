---
title: 憑證清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 若要指派憑證，請從本機憑證儲存區選取憑證。 按 [下一步] 繼續。
ms.openlocfilehash: d2a9d267542acb537f999e6946c406ca8e4c66a6617eca3da49366c9f8449814
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278881"
---
# <a name="certificate-list"></a>憑證清單
 
若要指派憑證，請從本機憑證儲存區選取憑證。 按 **[下一步]** 繼續。
  
在 [ **從本機憑證儲存區選取憑證** ] 窗格中，可供選取的憑證是可指派給您所需之憑證使用方式的有效憑證。 您可以按一下 [ **查看憑證詳細資料** ] 按鈕，確認您選取的憑證正確無誤。 在 [ **詳細資料** ] 索引標籤上，您可以查看憑證上所設定的主體名稱和主體備選項。
  
> [!IMPORTANT]
> 您可能不會在選取窗格中列出任何憑證。 發生這種情況時，一般原因是不會在預定的伺服器上安裝受信任的憑證授權單位憑證或中級憑證授權單位憑證，以驗證憑證，進而保證憑證所建立的信任鏈可供憑證授權單位單位使用。 若要解決此問題，請要求並匯入憑證鏈，該憑證鏈通常包含根憑證授權單位單位 (CA) 憑證和任何中間 CA 憑證，以及發行 CA 憑證。 
  

