---
title: 中繼服務設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 針對 [中繼伺服器]，您可以指定下列內容：
ms.openlocfilehash: e64343efa357caad2e843061574e5788a11db365
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582957"
---
# <a name="mediation-service-settings-expander"></a>中繼服務設定展開工具

針對 [中繼伺服器]，您可以指定下列內容：

若要組合轉送伺服器至前端集區或 Standard Edition 伺服器，請選取 [組合的中繼 **伺服器已啟用**] 核取方塊。 如果選擇不組合中繼伺服器，在此區段中就沒有可定義的設定。

如果您已啟用中繼伺服器的組合，則必須在伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。這是選用的設定，您應該參考閘道或公用交換電話網路 (PSTN) 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。

您定義與組合中繼伺服器相關聯的 PSTN 閘道。如果已經定義閘道，可以將其用來與中繼伺服器相關聯。

如果您有多個閘道與中繼伺服器相關聯，則第一個關聯的閘道將是預設閘道。如果需要選擇另一個閘道作為預設閘道，請選取您要作為預設的閘道，然後按一下 [成為預設]。若要取消成為預設的閘道，請按一下 [取消預設]。

如需定義及設定 Enterprise Edition 前端集區或 Standard Edition 伺服器之設定的詳細資訊，請參閱[定義及設定拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology)及[部署轉送伺服器及定義對等](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)。