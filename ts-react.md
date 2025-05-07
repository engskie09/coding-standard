// form.tsx
const Form = (props) => {
    const { prop } = props;

    // hook style here
    const styles = useStyles({ isSample });

    // hooks inside of the File
    const { useClick } = useButton();

    // hooks from external dependencies
    const navigate = useNavigate();
    const matches = useMatches();

    // hooks outside of the file but same directory
    const { form, handleOnSave } = useForm();

    // hooks outside of the File but same directory (with the consideration if nested directories)
    const { helper } = useFormMisc();

    // hooks from util: util/config util/helper util/store
    const dispatch = useAppDispatch();
    const { user } = useAppSelector((state) => state.globalCommon);

    // hooks from util: @/util/helper/api
    // it can be put in any lines just below of the upper rules. it could be on top or below of states or Effect

    // useState()
    const [mode, setMode] = useState(theme.palette.mode);

    // useEffect()
     useEffect(() => {
        setMode(theme.palette.mode);
    }, [theme.palette.mode]);

    // event handlers
    const handleOnClick = (): void => { };

    return <div/>;
};
