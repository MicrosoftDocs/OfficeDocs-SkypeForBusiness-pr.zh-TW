---
title: 檔共用的高可用性商務用 Skype Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 瞭解使用 DFS，以確保商務用 Skype Server 中檔案共用的高可用性。
ms.openlocfilehash: bd51464aa1588f672134c0d9ce5b2c8fc3faa97f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767521"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>檔共用的高可用性商務用 Skype Server
 
瞭解使用 DFS，以確保商務用 Skype Server 中檔案共用的高可用性。
  
為了確保您的商務用 Skype Server 部署中的檔案共用具有高可用性，您可以使用分散式檔案系統 (DFS) 。 DFS 支援在相同的資料中心內，從一個檔案伺服器到另一個檔案伺服器的容錯移轉。 在大規模部署中，建議您使用使用 DFS 成對的專用檔案伺服器。 如需 Windows Server 2012 中 DFS 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11)) 。 如需 Windows Server 2008 上之 DFS 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10)) 。
  
根據您的網路規模和您想要的復原數量，您可以使用一組伺服器來裝載網站中的所有檔案共用，或在前端集區中使用一對。
  
DFS 是一種最佳的檔複寫方式，沒有發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。 DFS 伺服器之間的容錯移轉應該會很快完成，但是資料複寫延遲可能會讓使用者無法繼續進行容錯移轉時進行中的工作。
  
如果您使用 DFS 和檔共用上的資料存放區很重要，您應該經常備份檔案共用，例如每4到8個小時。 當一個檔案共用停機且複寫不是最新時，您可以使用備份將失敗伺服器上的內容還原至與目前無法使用之伺服器配對的另一部伺服器。
