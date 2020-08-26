# ViewStub

    <androidx.appcompat.widget.ViewStubCompat
        android:id="@+id/uiStub"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:animateLayoutChanges="true"
        android:inflatedId="@+id/uiStub"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="parent" />

       class MainActivity , ViewStubCompat.OnInflateListener {


    fun onCreate(savedInstanceState: Bundle?, persistentState: PersistableBundle?) {
        super.onCreate(savedInstanceState, persistentState)

        inflateLayout(R.layout.firtView, this, "tag1")
        
    }


    @SuppressLint("RestrictedApi")
    fun inflateLayout(@LayoutRes res: Int, listener: ViewStubCompat.OnInflateListener?, tag: String) {

        if (listener != null) {
            binding.uiStub.setOnInflateListener(listener)
        }
        binding.uiStub.layoutResource = res

        binding.uiStub.tag = tag
        binding.uiStub.inflate()
    }


    override fun onInflate(stub: ViewStubCompat, inflated: View) {

        when (inflated.tag) {
            FIRST_SCREEN -> {
                updateFirstScreenView(inflated)
            }

        }//CHECK FOR TAG
    }

}
