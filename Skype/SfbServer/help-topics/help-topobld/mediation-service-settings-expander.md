---
title: 中繼服務設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 針對 [中繼伺服器]，您可以指定下列內容：
ms.openlocfilehash: e6b89c61e84577af86576850f5c675861cfa3a80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819555"
---
# <a name="mediation-service-settings-expander"></a>中繼服務設定展開工具

針對 [中繼伺服器]****，您可以指定下列內容：

如果您要將中繼伺服器 collocating 到前端池或標準版伺服器上，請選取 [**啟用中繼伺服器] Collocated**的核取方塊。 如果您選擇不 collocate 中繼伺服器，此區段中就沒有可定義的設定。

如果您已啟用中繼伺服器的 collocation，您必須在伺服器上定義 [傳輸層安全性（TLS）] 的偵聽埠範圍。 此連接埠預設為 5067。 如果您選取 [啟用 TCP 連接埠]****，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。 這是選用的設定，請參考閘道或公用交換電話網路 (PSTN) 需求來判斷是否需要這項設定。 依預設，TCP 連接埠的值為 5068。

您可以定義與 collocated 中繼伺服器相關聯的 PSTN 閘道。 如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。

如果您有多個與中繼伺服器關聯的閘道，第一個關聯的閘道就會是預設閘道。 如果需要選擇另一個閘道作為預設閘道，請選取您要作為預設的閘道，然後按一下 [成為預設]****。 若要取消成為預設的閘道，請按一下 [取消預設]****。

如需有關定義及設定企業版前端池或標準版伺服器設定的詳細資料，請參閱[定義及設定拓撲](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)及[部署轉送伺服器和定義對等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。


