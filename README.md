 = 
CALCULATE(
    COUNTROWS('Max'),
    FILTER(
        ALL('Max'[Customer Name]),
        'Max'[PO Date] = MAXX(ALL('Max'[Customer Name]), 'Max'[PO Date])
        && ('Max'[Exit Date] >= MAXX(ALL('Max'[Customer Name]), 'Max'[PO Date]) || ISBLANK('Max'[Exit Date]))
    )
)
