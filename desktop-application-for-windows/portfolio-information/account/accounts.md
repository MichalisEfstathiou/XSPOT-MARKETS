# Accounts

Accounts panel shows basic details about all accounts that are available for a user.

To open Accounts panel, select Account -&gt; Accounts in the header of the terminal:

![](../../../.gitbook/assets/10%20%285%29.png)

The Account panel is also available in Detailed view in order to show the detailed information in rows. You can see details about any of your accounts or about all together:

![](../../../.gitbook/assets/11%20%284%29.png)

If you have a Multi-asset account, then after selecting it in the Accounts lookup, the drop-down list will appear where you can select a needed asset to view detailed information and balance.

The following information about Accounts + calculation formulas is available:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Formula</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>General<b></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Balance</b></td>
      <td style="text-align:left">
        <br />A current realized balance of an account. If there is trading with pending
        valuation, balance won’t change before clearing, on which P/L will be credited
        by covered trades or delivery of funds will be performed by uncovered trades.
        Fees are charged off from a balance at the time of accrual.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Projected balance</b></td>
      <td style="text-align:left">A future balance which includes all accrued and not accrued profit/loss.
        After closing all positions, accrual of fees and assets' delivery, a balance
        becomes equal to a projected balance.</td>
      <td style="text-align:left">
        <p>
          <br />Projected balance = Balance + Unsettled cash + Loss + Profit + Blocked
          for Stocks + Option premium, where:</p>
        <ul>
          <li>Unsettled cash – cash sum of unsettled account operations, which have
            not been delivered to an account yet and will be delivered in accordance
            with T+n settlement system;</li>
          <li>Profit/Loss – current open profit/loss by positions;</li>
          <li>Blocked for Stocks – amount of funds debited from a balance in case of
            trading with symbols with Stocks pre-paid margin type. After closing such
            position, funds will be returned to an account:</li>
        </ul>
        <p>Blocked for stocks = abs (∑ Stock operation), abs - module.</p>
        <ul>
          <li>Option premium – option premium value which will be debited from or credited
            to an account while closing all positions for options with Option trading
            style 'Premium-style' or 'Mark-to-market'. Option trading style is set
            up by a broker:</li>
        </ul>
        <p>when 'Premium-style':
          <br />Option premium = ∑ (Open price * Qty * Lot size * Cross price), where:
          <br
          />Open price - an average price of a position opening;
          <br />Qty - a position's qty in lots;
          <br />Lot size = Tick cost / Tick size;
          <br />Cross price - an average cross price of a position opening for converting
          into account's currency.
          <br />
          <br />when 'Mark-to-market':
          <br />Option premium = ∑ (Current price * Qty * Lot size * Cross price), where:
          <br
          />Current price - a current option price, which depends upon 'Calculate
          PnL/margin from' set up by a broker for an instrument.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Balance & All risks</b></td>
      <td style="text-align:left">Shows actual current quantity of funds on an account which can be used
        for trading.</td>
      <td style="text-align:left">
        <p>
          <br />Balance&All risks = Balance + Loss + Profit + Unsettled cash + Unsettled
          cash for stocks + Unsettled option premium - Unused premium from open sell,
          where:</p>
        <ul>
          <li>Loss - current open losses, calculated for all instruments on a selected
            account.</li>
        </ul>
        <p>Loss isn't taken into account for 'Stocks pre-paid' margin type.</p>
        <p>For 'Securities fully paid' margin type Loss is taken into account for
          short positions, but isn't taken into account for long positions.</p>
        <p>For Options with Option trading style 'Premium-style' in buy positions
          Loss isn't taken into account.</p>
        <p>For Options with Option trading style 'Premium-style' in sell positions
          Loss is taken into account.</p>
        <p>For Options with Option trading style 'Mark-to-market' in buy positions
          Loss isn't taken into account.</p>
        <p>For Options with Option trading style 'Mark-to-market' in sell positions
          Loss is taken into account.</p>
        <p>Option trading style and margin type are set up by a broker.</p>
        <ul>
          <li>Profit - current open profit, calculated for all instruments on a selected
            account.</li>
        </ul>
        <p>Profit isn't taken into account for such margin types, as 'Security fully
          paid' and 'Stocks pre-paid'.</p>
        <p>Profit is taken into account for Options with Option trading style 'Premium-style'
          in buy positions.</p>
        <p>For Options with Option trading style 'Premium-style' in sell positions
          Profit isn't taken into account.</p>
        <p>For Options with Option trading style 'Mark-to-market' in buy positions
          Profit isn't taken into account.</p>
        <p>For Options with Option trading style 'Mark-to-market' in sell positions
          Profit is taken into account.</p>
        <p>Option trading style and margin type are set up by a broker.</p>
        <ul>
          <li>Unsettled cash – cash sum of unsettled account operations, which have
            not been delivered to an account yet and will be delivered in accordance
            with T+n settlement system;</li>
          <li>Unsettled cash for stocks = Unsettled positive cash for stocks + Used
            unsettled negative cash for stocks, where:</li>
        </ul>
        <p>Unsettled positive cash for stocks - value of unsettled cash, which was
          returned when selling stocks. For instruments with 'Stocks pre-paid' margin
          type. Is taken into account when 'Use unsettled positive cash for stocks
          in Margin available' is enabled by a broker for 'Stocks pre-paid' margin
          type;
          <br />Used unsettled negative cash for stocks - value of unsettled cash, blocked
          for instruments with 'Stocks pre-paid' margin type. Is taken into account
          when 'Use unsettled negative cash for stocks in Margin available' is disabled
          by a broker for 'Stocks pre-paid'.
          <br />
          <br />
        </p>
        <ul>
          <li>Unsettled option premium = Used unsettled negative premium + Unsettled
            positive premium - Unsettled premium from open sell, where:</li>
        </ul>
        <p>Used unsettled negative premium - unsettled negative option premium, which
          is taken into account when 'Use unsettled negative premium in Margin available'
          is enabled by a broker for such margin types, as 'Derivatives risk module'
          and 'CBOE';
          <br />Unsettled positive premium - unsettled positive option premium, which
          is taken into account when 'Use unsettled positive premium in Margin available'
          is enabled by a broker for such margin types, as 'Derivatives risk module'
          and 'CBOE';
          <br />Unsettled premium from open sell - unsettled uncovered option premium
          for opening short positions. It is taken into account when 'Use unsettled
          premium from open sell in Margin available' is enabled by a broker for
          such margin types, as 'Derivatives risk module' and 'CBOE' Unused premium
          from open sell - settled uncovered option premium for opening short positions,
          which is taken into account when 'Use premium from open sell in Margin
          available' is disabled by a broker for such margin types, as 'Derivatives
          risk module' and 'CBOE'.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Credit value</b></td>
      <td style="text-align:left">
        <br />An amount of credit funds which you can't withdraw, but can trade with.</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Available funds</b></td>
      <td style="text-align:left">Amount of funds which can be used for trading.</td>
      <td style="text-align:left">
        <br />Available funds = Balance&All risks - Initial margin req - Stock orders
        req</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Blocked balance</b></td>
      <td style="text-align:left">
        <br />Balance blocked by a broker or by a user for withdrawal\transfer.</td>
      <td
      style="text-align:left">Blocked balance = Withdrawal balance + Transfer balance</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Cash balance</b></td>
      <td style="text-align:left">
        <br />A current cash position for an account with taken into account unsettled
        profit/loss.</td>
      <td style="text-align:left">Cash balance = Balance + Unsettled cash</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Unsettled cash</b></td>
      <td style="text-align:left">
        <br />Cash sum of unsettled account operations, which have not been delivered
        to an account yet and will be delivered in accordance with T+n settlement
        system.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Withdrawal available</b></td>
      <td style="text-align:left">
        <br />Shows an amount of cash that you can withdraw immediately from your account.</td>
      <td
      style="text-align:left">
        <p>Withdrawal available = Available funds – Credit value – Profit – Unsettled
          profit + Unused unsettled negative cash for stocks – Unsettled positive
          cash for stocks + Unused unsettled negative premium - Unsettled positive
          premium + Unsettled premium from open sell - Used premium from open sell,
          where:</p>
        <ul>
          <li>Credit value - credited funds available to trade with but unavailable
            to withdraw;</li>
          <li>Profit - current open profit, calculated for all instruments on a selected
            account.</li>
        </ul>
        <p>
          <br />For such margin types, as 'Security fully paid' and 'Stocks pre-paid'
          Profit isn't taken into account.
          <br />
          <br />For Options with Option trading style 'Premium-style' in buy positions
          Profit is taken into account.
          <br />
          <br />For Options with Option trading style 'Premium-style' in sell positions
          Profit isn't taken into account.
          <br />
          <br />For Options with Option trading style 'Mark-to-market' in sell positions
          Profit is taken into account.
          <br />
          <br />For Options with Option trading style 'Mark-to-market' in buy positions
          Profit isn't taken into account.
          <br />
          <br />Option trading style is set up by a broker;</p>
        <ul>
          <li>Unsettled profit - realized profit for all positions, which has not been
            delivered to an account yet and will be delivered in accordance with T+n
            settlement system;</li>
          <li>Unused unsettled negative cash for stocks - value of unsettled cash, blocked
            for instruments with 'Stocks pre-paid' margin type. Is taken into account
            when 'Use unsettled negative cash for stocks in Margin available' is disabled
            by a broker for 'Stocks pre-paid' margin type;</li>
          <li>Unsettled positive cash for stocks - value of unsettled cash, which was
            returned when selling stocks. For instruments with 'Stocks pre-paid' margin
            type. Is taken into account when 'Use unsettled positive cash for stocks
            in Margin available' is enabled by a broker for 'Stocks pre-paid' margin
            type;</li>
          <li>Unused unsettled negative premium - unsettled negative option premium,
            which is taken into account when 'Use unsettled negative premium in Margin
            available' is disabled by a broker for such margin types, as 'Derivatives
            risk module' and 'CBOE';</li>
          <li>Unsettled positive premium - unsettled positive option premium, which
            is taken into account when 'Use unsettled positive premium in Margin available'
            is enabled by a broker for such margin types, as 'Derivatives risk module'
            and 'CBOE';</li>
          <li>Unsettled premium from open sell - unsettled uncovered option premium
            for opening short positions. It is taken into account when 'Use unsettled
            premium from open sell in Margin available' is enabled by a broker for
            such margin types, as 'Derivatives risk module' and 'CBOE';</li>
          <li>Used premium from open sell – settled uncovered option premium for opening
            short positions, which is taken into account when 'Use premium from open
            sell in Margin available' is enabled by a broker for such margin types,
            as 'Derivatives risk module' and 'CBOE'.</li>
        </ul>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Interest rate, %</b></td>
      <td style="text-align:left">Shows an annual interest rate on deposit.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Stocks value</b></td>
      <td style="text-align:left">
        <br />A total cost of assets, traded with Stocks pre-paid margin type, positions
        of which are open on a selected account.</td>
      <td style="text-align:left">Stocks value = ∑ (Current stock price * Amount * Cross price), where:
        <br
        />Amount - a current stocks' quantity in the position 'Qty * Lot size';
        Qty is qty in lots.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Stocks liquidity</b></td>
      <td style="text-align:left">
        <br />A part of a total cost of assets, which is accounted in available margin
        if there are assets on the account of a trader.</td>
      <td style="text-align:left">Stocks liquidity = ∑ (Amount * Price * CrossPrice * (Liquidity rate/100))
        <br
        />Amount - a current stocks' quantity on the account 'Qty * Lot size'; Qty
        is qty in lots.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Option value</b></td>
      <td style="text-align:left">
        <p>
          <br />Current option value in portfolio. Can be positive for a long Net position,
          or negative for a short Net position.</p>
        <p>Option value is calculated only for Options with Option trading style
          'Premium-style' or 'Mark-to-market'.
          <br />Option trading style is set up by a broker.</p>
      </td>
      <td style="text-align:left">Option value = ∑ (Current option price * Amount * Cross price), where:
        Current option price - a current price of an option, which depends upon
        'Calculate PnL/margin from' set up by a broker;
        <br />Amount - a current amount of options in a position;
        <br />Cross price - a current cross price in account's currency.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Margin</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Initial margin req.</b></td>
      <td style="text-align:left">
        <br />Amount of initial margin blocked for all positions and orders taking into
        account a margin crossing.</td>
      <td style="text-align:left">Initial margin req. = ∑ Initial margin req.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Initial margin req., %</b></td>
      <td style="text-align:left">
        <br />Shows how much margin is used in relation to Balance&All risks.</td>
      <td
      style="text-align:left">Initial margin req.,% = (Initial margin req. / (Balance&All risks - Stock
        orders req))*100%</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Maint. margin req., %</b></td>
      <td style="text-align:left">
        <br />Shows current level of risks. When Maint. margin req.=100%, stop-out triggers.</td>
      <td
      style="text-align:left">Maint. margin req. % = (Maint. margin req. / (Balance&All risks - Stock orders
        req))*100%</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Margin available</b></td>
      <td style="text-align:left">Full margin which is available to maintain a portfolio in a current moment.</td>
      <td
      style="text-align:left">Margin available = Balance&All risks - Maint. margin req. - Stock orders
        req</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Margin warning level</b></td>
      <td style="text-align:left">
        <br />Shows Maintenance margin level, which Warning margin message is sent with.</td>
      <td
      style="text-align:left">Warning margin lvl. = (Margin warning, % / 100) * (Balance&All risks -
        Stock orders req)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Stop out level, %</b></td>
      <td style="text-align:left">
        <br />Maintenance margin level value needed for the stop out to occur.</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Warning margin</b></td>
      <td style="text-align:left">
        <br />A value set on the account's level. When Maint. margin req., % reaches
        this value, a Warning margin message is sent.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Maint. margin req.</b></td>
      <td style="text-align:left">
        <br />Total margin used for maintenance of a current portfolio in account currency.</td>
      <td
      style="text-align:left">
        <br />Maint. margin req. = ∑ Maint. margin req.
        <br />(Maintenance margin req. for positions and Initial margin for orders, taking
        into account the margin crossing between orders and positions)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Blocked for Stocks</b></td>
      <td style="text-align:left">
        <br />Amount of funds debited from a balance in case of trading with symbols
        with Stocks pre-paid margin type. After closing such position, funds will
        be returned to an account. Stock operations can be pending.</td>
      <td style="text-align:left">Blocked for Stocks=abs(∑Stock operation), where:
        <br />abs - a module;
        <br />Stock operation = - Open price * Qty * Lot size * Cross price (for buy);
        <br
        />Stock operation = Open price * Qty * Lot size * Cross price (for sell).</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Stock orders req.</b></td>
      <td style="text-align:left">Total margin blocked for orders with Stock pre-paid margin type.</td>
      <td
      style="text-align:left">Stock orders req. = ∑ Margin for Stocks pre-paid orders</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Option premium req.</b></td>
      <td style="text-align:left">Option premium for buy orders</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Account activity</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Open gross P/L</b></td>
      <td style="text-align:left">
        <br />A profit or loss on all currently opened positions and currency, recalculated
        in real time based on the most recent quotes</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Open net P/L</b></td>
      <td style="text-align:left">
        <br />A net profit or loss on open positions.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Positions</b></td>
      <td style="text-align:left">A number of currently opened positions.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Orders</b></td>
      <td style="text-align:left">A number of currently placed pending orders.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today results</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's gross</b></td>
      <td style="text-align:left">A gross profit for today.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's net</b></td>
      <td style="text-align:left">A total profit or loss realized from positions today.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's fees</b></td>
      <td style="text-align:left">Fees paid today.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's volume</b></td>
      <td style="text-align:left">A total volume traded for today.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's trades</b></td>
      <td style="text-align:left">A number of trades done for today.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today turnover</b></td>
      <td style="text-align:left">Shows a turnover of funds per day for a current account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Today's rebates</b></td>
      <td style="text-align:left">
        <br />Shows a sum of all funds that have been received/paid by a broker for
        the creation/removal of liquidity for a current day. If a received rebates
        is bigger than a paid sum, then rebates value will be positive "+", otherwise
        negative "-".</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Risk management</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Trading status</b></td>
      <td style="text-align:left">Trading status of a selected account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Daily loss limit</b></td>
      <td style="text-align:left">Max loss limit for 1 day, trading is blocked when this limit is reached.</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Weekly loss limit</b></td>
      <td style="text-align:left">Max loss limit for 1 week, trading is blocked when this limit is reached.</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Daily profit target</b></td>
      <td style="text-align:left">
        <br />Maximum value of daily net profit allowed for an account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Total max position qty</b></td>
      <td style="text-align:left">Max total qty in lots of all positions and orders.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Trailing drawdown level</b></td>
      <td style="text-align:left">Shows maximum drawdown level for an account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Daily loss</b></td>
      <td style="text-align:left">
        <br />Shows a current net daily loss limit value for an account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Weekly loss</b></td>
      <td style="text-align:left">
        <br />Shows a current net weekly loss limit value for an account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Max. day volume</b></td>
      <td style="text-align:left">Shows a Max. day volume set for an account.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Max. positions</b></td>
      <td style="text-align:left">Shows a Max. qty. of positions.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Max. pending orders</b></td>
      <td style="text-align:left">Shows a Max. qty of pending orders.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Max. orders capital</b></td>
      <td style="text-align:left">Shows a Max. order capital.</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Allow overnight trading</b></td>
      <td style="text-align:left">
        <br />Shows whether it is allowed or not to transfer positions through night
        for an account.</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>
