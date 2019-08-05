---
title: 遷移類比裝置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 商務用 Skype 伺服器提供類比裝置的支援。 具體說來, 支援的類比裝置是類比音訊電話和類比傳真電腦。 您可以設定合格的閘道, 以支援在商務用 Skype Server 環境中使用類比裝置。 在您遷移到商務用 Skype Server 2019 之後, 您也必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server Management 命令介面, 先檢索與舊版類比裝置相關聯的所有連絡人物件, 然後將這些物件移到商務用 Skype Server 2019 池。
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189085"
---
# <a name="migrate-analog-devices"></a>遷移類比裝置

商務用 Skype 伺服器提供類比裝置的支援。 具體說來, 支援的類比裝置是類比音訊電話和類比傳真電腦。 您可以設定合格的閘道, 以支援在商務用 Skype Server 環境中使用類比裝置。 在您遷移到商務用 Skype Server 2019 之後, 您也必須遷移與類比裝置相關聯的連絡人物件。 使用商務用 Skype Server Management 命令介面, 先檢索與舊版類比裝置相關聯的所有連絡人物件, 然後將這些物件移到商務用 Skype Server 2019 池。

### <a name="to-migrate-analog-devices"></a>遷移類比裝置

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。

2. 在命令列中, 輸入:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. 確認所有連絡人物件都已移至商務用 Skype Server 2019 池。 在命令列中, 輸入:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. 確認所有連絡人物件現在都與商務用 Skype Server 2019 池相關聯。


